<template>
  <div>
    <header class="hero"></header>
    <div class="flex justify-center">
      <div class="w-3/5">
        <form
          id="popRdv"
          class="flex flex-col bg-white p-10 rounded-lg shadow-lg min-w-full"
          @submit.prevent
        >
          <h1
            class="text-center text-2xl mb-6 text-gray-600 font-bold font-sans"
          >Prendre un rendez-vous</h1>
          <div>
            <label class="text-left text-gray-800 font-semibold block my-3" for="Sujet">Sujet :</label>
            <input
              class="w-full bg-gray-100 px-4 py-2 rounded-lg focus:outline-none"
              type="textarea"
              name="Sujet"
              v-model="RDVform.Sujet"
              id="Sujet"
              placeholder="Sujet"
            />
          </div>
          <div>
            <label
              class="text-left text-gray-800 font-semibold block my-3 text-md"
              for="date"
            >Date :</label>
            <input
              @change="checkhour"
              class="w-full bg-gray-100 px-4 py-2 rounded-lg focus:outline-none"
              type="date"
              name="date"
              v-model="RDVform.date"
              :min="new Date().toISOString().substr(0, 10)"
              id="date"
            />
          </div>
          <div v-if="RDVform.date">
            <label
              class="text-left text-gray-800 font-semibold block my-3 text-md"
              for="date"
            >Créneaux:</label>
            <select
              class="select select-bordered w-full bg-gray-100 px-4 py-2 rounded-lg focus:outline-none mb-4"
              name="creneau"
              v-model="RDVform.creneau"
            >
              <option selected disabled >Choisissez l'heure à laquelle vous aimeriez vous rencontrer</option>
              <option v-for="hor in hour" :key="hor">{{ hor }}</option>
            </select>
          </div>
          <input
            type="submit"
            value="Confirmer"
            @click="addAppointment()"
            class="py-3 px-5 mt-auto rounded-md text-white bg-sky-600 hover:bg-blue-300 hover:text-blue-900 transition-all justify-self-end"
          />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "hafidH",
  data() {
    return {
      RDVform: {
        id_utilisateur: localStorage.getItem("id"),
        Sujet: "",
        date: "",
        creneau: "",
      },
      hour: [],
    };
  },
  methods: {
    addAppointment() {
      fetch("http://localhost/BRIEFS_6/user/addAppointment", {
        method: "POST",
        body: JSON.stringify(this.RDVform),
      })
        .then((result) => {
          return result.json();
        })
        .then((data) => {
          if (data) {
            this.$router.push("/User");
          }
        });
    },
    checkhour() {
      fetch(`http://localhost/BRIEFS_6/User/selectInDate?date="${this.RDVform.date}"`, {
        method: "GET",
      })
        .then((result) => {
          return result.json();
        })
        .then((data) => {
          this.hour = data;
        });
    }
  },
};
</script>
<style>
#popRdv {
  height: 450px;
}
#title {
  font-size: 1.5rem;
  font-family: "Courier New", Courier, monospace;
  color: rgb(0, 0, 0);
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>