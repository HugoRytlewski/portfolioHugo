<script setup lang="ts">
import NavbarProjet from '../components/Layouts/NavBarProjet.vue';
import Footer from '../components/Layouts/Footer.vue';
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})
const showHtml = ref(false);
const showPhp = ref(false);
const ShowCss = ref(false);

</script>
<template>
  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 md:mt-28 flex flex-col justify-center items-center">
        <img class="w-2/5 h-3/6 rounded-lg md:w-auto" src="~/assets/img/logo.png" alt="resto">

        <div class="mt-12 md:mt-28 w-3/5 border-b-2 pb-4 border-white">
          <h1 class="text-4xl text-red-500">RESTO.FR</h1>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-red-500">Résumé</h1>
          <div>
            <span class="text-2xl text-white">Resto.fr est un projet de référencement de restaurants. C'est un projet sur lequel j'ai travaillé pendant mon BTS SIO.</span>
          </div>
        </div>
            <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-red-500">Mission(s)</h1>
          <div class="flex flex-col">
            <span class="text-2xl text-white">- Ajout de la fonctionnalité "Ajout aux favoris". </span>
            <br>
            <span class="text-2xl text-white">- Ajout de la fonctionnalité "Espace de recherche".</span>

          </div>
          <div >

          <span class="text-2xl text-white">- Ajout de la fonctionnalité "Commentaires". </span>
          <br>
          <span class="text-2xl text-white">- Ajout de la fonctionnalité "Connexion".</span>
        </div>
        </div>
        <div class="h-16 mt-8 md:mt-10 w-3/5 gap-10 md:flex ">
          <h1 class="text-3xl text-red-500 ">Technologies</h1>
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
              <img @click="showPhp=!showPhp" class="cursor-pointer w-16 h-10" src="~/assets/img/php.png" alt="php">
              <span v-if="showPhp" class="text-white text-xl mt-2">PHP</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-20 ml-4 mr-4 md:ml-0 md:mr-0 ">
  

  <div id="controls-carousel" class="relative w-full" data-carousel="static">
<div class="relative h-56 overflow-hidden rounded-lg md:h-96">
    <div class="hidden duration-700 ease-in-out" data-carousel-item>
        <img src="~/assets/img/resto.png" class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2" alt="">
    </div>
    <div class="hidden duration-700 ease-in-out" data-carousel-item="active">
        <img src="~/assets/img/test.png" class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2" alt="">
    </div>
   
</div>
<div class="flex justify-center items-center pt-4">
    <button type="button" class="flex justify-center items-center mr-4 h-full cursor-pointer group focus:outline-none" data-carousel-prev>
        <span class="text-gray-400 hover:text-white group-focus:text-white ">
            <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 5H1m0 0 4 4M1 5l4-4"/>
            </svg>
        </span>
    </button>
    <button type="button" class="flex justify-center items-center h-full cursor-pointer group focus:outline-none" data-carousel-next>
      <span class="text-gray-400 hover:text-white group-focus:text-white ">
            <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
            </svg>
        </span>
    </button>
</div>
</div>


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


    
  
