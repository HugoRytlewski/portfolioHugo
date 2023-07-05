<script setup lang="ts">
import NavbarProjet from '../components/Layouts/NavBarProjet.vue';
import Footer from '../components/Layouts/Footer.vue';

const showHtml = ref(false);
const showNuxt = ref(false);
const ShowCss = ref(false);
const ShowSymfony = ref(false);
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img class="w-2/5 h-3/6 rounded-lg md:w-auto" src="~/assets/img/icon-nexton.png" alt="nexton">
        <div class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white">
          <h1 class="text-4xl text-blue-500">NEXTFEED</h1>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-blue-500">Résumé</h1>
          <div>
            <span class="text-2xl text-white">Nextfeed est un projet de veille informatique, sur lequel j'ai travaillé pendant mon stage chez Nexton.</span>
          </div>
        </div>
        <div class="h-16 mt-8 md:mt-10 w-3/5 gap-10 md:flex ">
          <h1 class="text-3xl text-blue-500">Technologies</h1>
          <div class="gap-4 mt-5 flex flex-wrap justify-start md:justify-start md:mt-0">
            <div class="flex flex-col items-center">
              <img @click="ShowCss=!ShowCss" class="cursor-pointer w-10 h-10" src="~/assets/img/css.png" alt="css">
              <span v-if="ShowCss" class="text-white text-xl mt-2">CSS</span>
            </div>
            <div class="flex flex-col items-center">
              <img @click="showHtml=!showHtml" class="cursor-pointer w-10 h-10" src="~/assets/img/html.png" alt="html">
              <span v-if="showHtml" class="text-white text-xl mt-2">HTML</span>
            </div>
            <div class="flex flex-col items-center">
              <img @click="showNuxt=!showNuxt" class="cursor-pointer w-10 h-10" src="~/assets/img/icon-green.svg" alt="nuxt">
              <span v-if="showNuxt" class="text-white text-xl mt-2">NUXT</span>
            </div>
            <div class="flex flex-col">
              <img @click="ShowSymfony=!ShowSymfony" class="ml-1.5 cursor-pointer w-10 h-10" src="~/assets/img/symfony.svg" alt="symfony">
              <span v-if="ShowSymfony" class="text-white text-xl mt-2">SYMFONY</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-16" >

    </div>
    <Footer />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');

h1 {
  font-family: 'VT323', monospace;
}

span {
  font-family: 'VT323', monospace;
}
</style>
