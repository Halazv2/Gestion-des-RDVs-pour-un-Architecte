<template>
  <div>
    <section class="container mx-auto p-6 font-mono">
      <div class="w-full mb-8 overflow-hidden rounded-lg shadow-lg">
        <div class="w-full overflow-x-auto">
          <div id="Alluser" class="pb-6 text-xl font-bold">
            All User ☜(ﾟヮﾟ☜)
          </div>
          <table class="w-full">
            <thead>
              <tr
                class="
                  text-md
                  font-semibold
                  tracking-wide
                  text-left text-gray-900
                  bg-gray-100
                  uppercase
                  border-b border-gray-600
                "
              >
                <th id="add" class="px-4 py-3">id</th>
                <th id="add" class="px-4 py-3">Name</th>
                <th id="add" class="px-4 py-3">Age</th>
                <th id="add" class="px-4 py-3">Status</th>
                <th id="add" class="px-4 py-3">CIN</th>
                <th id="add" class="px-4 py-3">Action</th>
              </tr>
            </thead>
            <tbody class="bg-white">
              <tr v-for="user in Alluser" :key="user.id" class="text-gray-700">
                <td class="px-4 py-3 text-ms font-semibold border">
                  {{ user.id }}
                </td>

                <td class="px-4 py-3 border">
                  <div class="flex items-center text-sm">
                    <div class="relative w-8 h-8 mr-3 rounded-full md:block">
                      <img
                        class="object-cover w-full h-full rounded-full"
                        src="https://images.pexels.com/photos/5212324/pexels-photo-5212324.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260"
                        alt
                        loading="lazy"
                      />
                      <div
                        class="absolute inset-0 rounded-full shadow-inner"
                        aria-hidden="true"
                      ></div>
                    </div>
                    <div>
                      <p class="font-semibold text-black">
                        {{ user.Nom }} {{ user.Prenom }}
                      </p>
                    </div>
                  </div>
                </td>
                <td class="px-4 py-3 text-ms font-semibold border">
                  {{ user.Age }}
                </td>
                <td class="px-4 py-3 text-xs border">
                  <h3>{{ user.Job }}</h3>
                </td>
                <td class="px-4 py-3 text-sm border">{{ user.CIN }}</td>
                <td class="px-4 py-3 text-sm border">
                  <a class="dlete text-[#FF0000]" @click="deleteUser(user.id)"
                    >Delete</a
                  >
                  &nbsp;
                  <a @click="getUser(user.id)" class="text-[#088F8F]">Edit</a>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>
    <com-update-user
      v-if="!popUserF"
      class="popap"
      @close="close"
      @getOneUser="getOneUser"
      :UserIDupdate="UserIDupdate"
    />
  </div>
</template>

<script>
import ComUpdateUser from "./ComUpdateUser.vue";

export default {
  components: { ComUpdateUser },
  name: "All-users",
  data() {
    return {
      Alluser: [],
      popUserF: true,
      id: "",
      UserIDupdate: "",
    };
  },
  methods: {
    GetAllUser() {
      fetch("http://localhost/BRIEFS_6/Admin/UserAll", {
        method: "GET",
      })
        .then((result) => {
          return result.json();
        })
        .then((reponse) => {
          this.Alluser = reponse;
        });
    },
    deleteUser(id) {
      fetch(`http://localhost/BRIEFS_6/admin/DELETEUSER?id=${id}`, {
        method: "DELETE",
      }).then(() => {
        this.GetAllUser();
      });
    },
    getOneUser() {
      fetch(
        `http://localhost/BRIEFS_6/admin/getOneUser?id="${this.UserIDupdate}"`,
        {
          method: "GET",
        }
      ).then((result) => {
        return result.json();
      });
    },
    check() {
      if (localStorage.getItem("role") === null) {
        this.$router.push("/");
      } else if (localStorage.getItem("role") === "admin") {
        this.$router.push("/admin");
      } else {
        this.$router.push("/User");
      }
    },
    close() {
      this.popUserF = !this.popUserF;
      this.GetAllUser();
    },
    getUser(id) {
      this.popUserF = !this.popUserF;
      this.UserIDupdate = id;
    },
  },
  mounted() {
    this.check();
    this.GetAllUser();
  },
};
</script>

<style>
#Alluser {
  font-size: 1.5rem;
  font-family: "Courier New", Courier, monospace;
  color: rgb(0, 0, 0);
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}
.dlete {
  color: red;
  cursor: pointer;
}
.dlete:hover {
  color: rgba(181, 46, 46, 0.577);
}
#add {
  text-align: center;
  color: darkslateblue;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
.popap {
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.359);
  position: absolute;
  top: 0%;
  left: 0%;
}
</style>