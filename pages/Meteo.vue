<script setup>
import NavbarProjet from "../components/Layouts/NavBarProjet.vue";
import Footer from "../components/Layouts/Footer.vue";
import { onMounted } from "vue";
import { initFlowbite } from "flowbite";

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});
const showHtml = ref(false);
const ShowCss = ref(false);
const showNuxt = ref(false);

const Image = ref(true);

</script>
<template>
  <title>Projet Météo</title>

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center ">
        <img
          class="w-2/5 h-3/6 rounded-xl md:w-auto bg-white p-6 "
          src="~/assets/img/meteo.ico "
          alt="collection-logo"
        />
        <div
          class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
        >
          <h1 class="text-4xl text-white">Météo</h1>
          <div class="flex gap-2">
            <a class="text-white text-xl md:text-2xl">Consulter le site </a>

            <a
              class="text-white text-xl md:text-2xl underline underline-offset-8"
              href="https://meteo-app-peach.vercel.app"
              target="_blank"
              >ici
            </a>
            <a
              class="text-white text-xl md:text-2xl"
              href="https://meteo-app-peach.vercel.app"
              target="_blank"
              >!
            </a>
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >Météo est un projet personnel qui montre la réalisation d'un site
              de météo.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white md:text-center"
              >Ajout de barre de recherche pour chercher une ville: elle permet
              à l'utilisateur de choisir une ville pour consulter sa météo
              .</span
            >
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Ajout d'information supplémentaire : cela permet à l'utilisateur
              de voir l'humidite , la temperature minimum et maximum.
            </span>
          </div>
        </div>
        <div class="h-16 mt-8 md:mt-10 w-3/5 gap-10 md:flex">
          <h1 class="text-3xl text-white">Technologies</h1>
          <div
            class="gap-4 mt-5 flex flex-wrap justify-start md:justify-start md:mt-0"
          >
            <div class="flex flex-col items-center">
              <img
                @click="ShowCss = !ShowCss"
                class="cursor-pointer w-10 h-10"
                src="~/assets/img/css.png"
                alt="css"
              />
              <Transition>
                <span v-if="ShowCss" class="text-white text-xl mt-2">CSS</span>
              </Transition>
            </div>
            <div class="flex flex-col items-center">
              <img
                @click="showHtml = !showHtml"
                class="cursor-pointer w-10 h-10"
                src="~/assets/img/html.png"
                alt="html"
              />
              <Transition>
                <span v-if="showHtml" class="text-white text-xl mt-2"
                  >HTML</span
                >
              </Transition>
            </div>
            <div class="flex flex-col items-center">
              <img
                @click="showNuxt = !showNuxt"
                class="cursor-pointer w-10 h-10"
                src="~/assets/img/icon-green.svg"
                alt="nuxt"
              />
              <Transition>
                <span v-if="showNuxt" class="text-white text-xl mt-2"
                  >NUXT</span
                >
              </Transition>
            </div>
            <div class="flex flex-col items-center"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div></div>
  <div class="mt-24 xl:mt-10 ml-4 mr-4 md:ml-0 md:mr-0">
    <div class="relative w-full">
      <div class="relative h-56 overflow-hidden rounded-lg md:h-96">
        <div class="duration-300 ease-in-out">
          <Transition name="image"> 

          <img
            v-if="Image"
            @click="Image = !Image"
            src="~/assets/img/appmeteo.png"
            class="cursor-pointer object-contain	absolute block max-w-full h-96 -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-collection"
          />
    

          <img
            v-else
            @click="Image = !Image"
            src="~/assets/img/appmeteo.png"
            class="cursor-pointer object-contain	fixed block max-w-full h-[80vh] -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-collection"
          />
        </Transition>

        </div>
      </div>
    </div>
  </div>
  <Footer />
</template>
<style>
  @import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

.image-enter-active,
.image-leave-active {
transition: all 0.5s ease;
}

.image-enter-from,
.image-leave-to {
opacity: 0;
transform: scale(0.5);
}
.v-enter-active,
.v-leave-active {
  transition: all 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
  transform: translateY(-100%);
}
h1 {
  font-family: "VT323", monospace;
}

span {
  font-family: "VT323", monospace;
}
</style>