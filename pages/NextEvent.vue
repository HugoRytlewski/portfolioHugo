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
  <title>Projet NextEvent</title>

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img
          class="w-2/5 h-3/6 rounded-lg md:w-auto"
          src="~/assets/img/icon-nexton.png"
          alt="nexton"
        />
        <div
        class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
      >
        <h1 class="text-4xl text-blue-500">NextEvent</h1>
        <div class="  flex">
          <p class="text-2xl  text-white">Doc Dispo :</p>
          <a class="text-white" href="https://docs.google.com/document/d/1R93OHfE6UrLr69pC7nmPPV3zC_ZH9bv47zvsvBi-J2o/edit?usp=sharing" target="_blank"><img class="h-10 " src="~/assets/img/doc.png" alt=""></a>

      </div>
      </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-blue-500">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >NextEvents est une plateforme en ligne de gestion et de planification d’évènements internes (meetup, workshop, formation, etc…), ainsi que de gestion de participation.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-blue-500">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white"
              >Creation du backend sur symfony a partir d'un workflow
            </span>
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Creation du frontend avec Nuxt.js et TailwindCSS a partir d'un figma design
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