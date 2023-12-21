<script setup lang="ts">
import NavbarProjet from "../components/Layouts/NavBarProjet.vue";
import Footer from "../components/Layouts/Footer.vue";
import { onMounted } from "vue";
import { initFlowbite } from "flowbite";

// initialize components based on data attribute selectors
onMounted(() => {
  initFlowbite();
});
const showHtml = ref(false);
const showNuxt = ref(false);
const ShowCss = ref(false);
const ShowSymfony = ref(false);

const Image = ref(true);
const Image2 = ref(true);
</script>

<template>
  <title>Projet NEXTFEED</title>

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img
          class="w-2/5 h-3/6 rounded-lg md:w-auto"
          src="~/assets/img/icon-nexton.png"
          alt="nexton"
        />
        <div class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white">
          <h1 class="text-4xl text-blue-500">NEXTFEED</h1>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-blue-500">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >Nextfeed est un projet de veille informatique, sur lequel j'ai
              travaillé pendant mon stage chez Nexton.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-blue-500">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white"
              >Ajout de la gestion des flux RSS préférés par l'utilisateur :
              Cette fonctionnalité permet à l'utilisateur de sélectionner et de
              gérer ses flux RSS préférés.
            </span>
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Ajout de la connexion avec Google : Cette fonctionnalité permet à
              l'utilisateur de se connecter à votre application ou système en
              utilisant son compte Google.
            </span>
          </div>
        </div>
        <div class="h-16 mt-8 md:mt-10 w-3/5 gap-10 md:flex">
          <h1 class="text-3xl text-blue-500">Technologies</h1>
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
            <div class="flex flex-col">
              <img
                @click="ShowSymfony = !ShowSymfony"
                class="ml-1.5 cursor-pointer w-10 h-10"
                src="~/assets/img/symfony.svg"
                alt="symfony"
              />
              <Transition>
                <span v-if="ShowSymfony" class="text-white text-xl mt-2"
                  >SYMFONY</span
                >
              </Transition>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div></div>
  <div class="mt-24 xl:mt-10 ml-4 mr-4 md:ml-0 md:mr-0">
    <div id="controls-carousel" class="relative w-full" data-carousel="static">
      <div class="relative h-56 overflow-hidden rounded-lg md:h-96">
        <div class="hidden duration-700 ease-in-out" data-carousel-item>
          <img
            v-if="Image"
            @click="Image = !Image"
            src="~/assets/img/nextfeed.png"
            class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-nextfeed1"
          />
        </div>
        <div
          class="hidden duration-700 ease-in-out"
          data-carousel-item="active"
        >
          <img
            v-if="Image2"
            @click="Image2 = !Image2"
            src="~/assets/img/nextfeed2.png"
            class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-nextfeed2"
          />
        </div>
      </div>
      <div class="flex justify-center items-center pt-4">
        <button
          type="button"
          class="flex justify-center items-center mr-4 h-full cursor-pointer group focus:outline-none"
          data-carousel-prev
        >
          <span class="text-gray-400 hover:text-white group-focus:text-white">
            <svg
              class="w-5 h-5"
              aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 14 10"
            >
              <path
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M13 5H1m0 0 4 4M1 5l4-4"
              />
            </svg>
          </span>
        </button>
        <button
          type="button"
          class="flex justify-center items-center h-full cursor-pointer group focus:outline-none"
          data-carousel-next
        >
          <span class="text-gray-400 hover:text-white group-focus:text-white">
            <svg
              class="w-5 h-5"
              aria-hidden="true"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 14 10"
            >
              <path
                stroke="currentColor"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M1 5h12m0 0L9 1m4 4L9 9"
              />
            </svg>
          </span>
        </button>
      </div>
    </div>
  </div>
  <Footer />
  <Transition name="image">
    
    <img
    v-if="!Image"

      @click="Image = !Image"
      src="~/assets/img/nextfeed.png"
      class="z-50 cursor-zoom-out object-contain fixed block max-w-full h-[80vh] -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
      alt="screen-resto2"
    />
</Transition>
<Transition name="image">
    
    <img
    v-if="!Image2"

      @click="Image2 = !Image2"
      src="~/assets/img/nextfeed2.png"
      class="z-50 cursor-zoom-out object-contain fixed block max-w-full h-[80vh] -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
      alt="screen-resto2"
    />
</Transition>

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