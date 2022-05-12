<template>
  <div>
    <header>
      <div
        class="bg-gray-100"
        style="
          background-image: url(https://images.pexels.com/photos/911758/pexels-photo-911758.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940);
          background-size: 100% 100%;
        "
      >
        <div class="hero-overlay bg-opacity-60">
          <div class="mx-auto flex flex-col items-center py-12 sm:py-24">
            <div
              class="
                w-11/12
                sm:w-2/3
                lg:flex
                justify-center
                items-center
                flex-col
                mb-5
                sm:mb-10
              "
            >
              <h1
                class="
                  text-2xl
                  sm:text-3xl
                  md:text-4xl
                  lg:text-5xl
                  xl:text-6xl
                  text-center text-gray-800
                  font-black
                  leading-7
                  md:leading-10
                  text-sky-100
                "
              >
                The Freedom to Create the
                <span class="text-sky-500">Home</span>
                You Want
              </h1>
              <p
                class="
                  mt-5
                  sm:mt-10
                  lg:w-10/12
                  text-gray-100
                  font-normal
                  text-center text-sm
                  sm:text-lg
                "
              >
                Nous avons ce dont vous avez besoin!
              </p>
            </div>
            <div class="flex justify-center items-center">
              <button
              @click="pushauth"
                class="
                  focus:outline-none
                  focus:ring-2
                  focus:ring-offset-2
                  focus:ring-indigo-700
                  bg-sky-500
                  transition
                  duration-100
                  uppurcase
                  ease-in-out
                  hover:bg-sky-600
                  lg:text-xl lg:font-bold
                  rounded
                  text-white
                  px-4
                  sm:px-10
                  border border-sky-600
                  py-2
                  sm:py-4
                  text-sm
                "
              >
                RESERVER un randiveu
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-gray-100">
        <div
          class="container mx-auto flex flex-col items-center py-12 sm:py-24"
        >
          <div>
            <h1 class="text-6xl font-medium no-underline md:underline mb-20">
              About Us
            </h1>
          </div>
          <div class="flex justify-center items-center">
            <div>
              <i icon="fa-solid fa-gem" />
              <p class="w-[80%] text-center">
                Nous sommes une Agence d'Architecture basée à Safi - Maroc,
                fondée Yasser RACHID, Architecte Diplomé par l'Ecole Nationale
                d'Architecture de Rabat. Nous travaillons sur les projets
                d'Architecture, d'Urbanisme et de Design; Nous couvrons un large
                spectre de typologies, d'échelles et de styles. Notre approche
                collaborative et analytique a pour but de répondre à un
                programme physique ainsi qu'un concept. Notre philosophie de
                travail est de développer des solutions Contemporaines,
                Intelligentes et Innovantes.
              </p>
            </div>
            <img
              src="https://www.yasserrachid.com/img/portfolio/thumbnails/46.jpg"
              alt
            />
          </div>
        </div>
      </div>
      <div class="container mx-auto flex flex-col items-center py-12 sm:py-24">
        <div>
          <h1 class="text-6xl font-medium no-underline md:underline mb-20">
            NOUS CONTACTER
          </h1>
          <div class="container flex gap-60 justify-center items-center">
            <div class="w-2/5 flex flex-col justify-center items-center">
              <img
                class="svg"
                src="https://about.crunchbase.com/wp-content/uploads/2021/03/Community_FAQ-1.svg"
              />
              <!-- <p> 
                Etes-vous prêt à rêver votre projet avec nous? Nous vous
                invitons à prendre RENDEZ-VOUS via Notre sitewebe, E-Mail ou
                Téléphone. Nous serons heureux de vous accueillir et de vous
                accompagner pour concretiser vos idées.
              </p>
              <br />
              <div class="flex flex-col">
                <span class="text-sky-500"
                  >+212(0)660-655328 (Tél & WhatsApp)</span
                >
                <span class="text-sky-500"
                  >hafid.Benhfid.Architecte@gmail.com</span
                >
              </div> -->
            </div>
            <div>
              <form class="w-full max-w-lg text-left">
                <div class="flex flex-wrap -mx-3 mb-6">
                  <div class="w-full md:w-1/2 px-3 md:mb-0">
                    <label
                      class="
                        block
                        uppercase
                        tracking-wide
                        text-gray-700 text-xs
                        font-bold
                      "
                      for="grid-first-name"
                    >
                      First Name
                    </label>
                    <input
                      class="
                        appearance-none
                        block
                        w-full
                        bg-gray-200
                        text-gray-700
                        rounded
                        py-3
                        px-4
                        leading-tight
                        focus:outline-none focus:bg-white
                      "
                      id="grid-first-name"
                      type="text"
                      placeholder="Jane"
                    />
                  </div>
                  <div class="w-full md:w-1/2 px-3">
                    <label
                      class="
                        block
                        uppercase
                        tracking-wide
                        text-gray-700 text-xs
                        font-bold
                      "
                      for="grid-last-name"
                    >
                      Last Name
                    </label>
                    <input
                      class="
                        appearance-none
                        block
                        w-full
                        bg-gray-200
                        text-gray-700
                        border border-gray-200
                        rounded
                        py-3
                        px-4
                        leading-tight
                        focus:outline-none focus:bg-white focus:border-gray-500
                      "
                      id="grid-last-name"
                      type="text"
                      placeholder="Doe"
                    />
                  </div>
                </div>
                <div class="flex flex-wrap -mx-3 mb-6">
                  <div class="w-full px-3 ">
                    <label
                      class="
                        block
                        uppercase
                        tracking-wide
                        text-gray-700 text-xs
                        font-bold
                        
                      "
                      for="grid-password"
                    >
                      E-mail
                    </label>
                    <input
                      class="
                        appearance-none
                        block
                        w-full
                        bg-gray-200
                        text-gray-700
                        border border-gray-200
                        rounded
                        py-3
                        px-4
                        leading-tight
                        focus:outline-none focus:bg-white focus:border-gray-500
                      "
                      id="email"
                      type="email"
                    />
                  </div>
                </div>
                <div class="flex flex-wrap -mx-3 mb-6">
                  <div class="w-full px-3">
                    <label
                      class="
                        block
                        uppercase
                        tracking-wide
                        text-gray-700 text-xs
                        font-bold
                      "
                      for="grid-password"
                    >
                      Message
                    </label>
                    <textarea
                      class="
                        no-resize
                        appearance-none
                        block
                        w-full
                        bg-gray-200
                        text-gray-700
                        border border-gray-200
                        rounded
                        py-3
                        px-4
                        leading-tight
                        focus:outline-none focus:bg-white focus:border-gray-500
                        h-48
                        resize-none
                      "
                      id="message"
                    ></textarea>
                  </div>
                </div>
                <div class="md:flex md:items-center">
                  <div class="md:w-1/3">
                    <button
                      class="
                        focus:outline-none focus:ring-2 focus:ring-offset-2
                        bg-sky-500
                        transition
                        duration-100
                        ease-in-out
                        hover:bg-sky-600
                        rounded
                        text-white
                        p-2
                        py-2
                        border border-sky-600
                      "
                      type="button"
                    >
                      Send
                    </button>
                  </div>
                  <div class="md:w-2/3"></div>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-gray-100 p-14">
        <p>Copyright © 2022 - Meknasi & Hala</p>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: "homeComponent",
  methods: {
    pushauth(){
      this.$router.push('/');
    }
  },
};
</script>

<style>
.hero {
  width: 100%;
  height: 100%;
  background-size: 100% 50%;
  background-repeat: no-repeat;
}
.qskd {
  display: flex;
  flex-direction: column;
}
.svg {
  height: 560px;
  width: 810px;
}
</style>