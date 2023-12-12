<script setup>
import NavbarProjet from "../components/Layouts/NavBarProjet.vue";
import Footer from "../components/Layouts/Footer.vue";
import { onMounted } from "vue";
import { initFlowbite } from "flowbite";

onMounted(() => {
  initFlowbite();
});
const showHtml = ref(false);
const ShowCss = ref(false);
const showJSON = ref(false);
</script>
<template>
  <title>Projet Seminaire JSON</title>
<div class="w-screen overflow-hidden">

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img
          class="w-2/5 h-3/6 rounded-xl md:w-auto"
          src="~/assets/img/JsonSeminaire.ico "
          alt="collection-logo"
        />
        <div
          class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
        >
          <h1 class="text-4xl text-white">Projet Seminaire JSON</h1>
          <div class="  md:flex">
            <p class="text-2xl  text-white">Doc Dispo :</p>
            <a class="text-white" href="https://docs.google.com/document/d/1xF4Np9bvDLm41-A-uWegjP92tyKWoD9vLmB3EZNqxTU/edit?usp=sharing" target="_blank"><img class="h-10 " src="~/assets/img/doc.png" alt=""></a>

        </div>
        </div>

        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >C'est un projet réalisé dans le cadre du Cours BLOC2 au sein de
              ma formation BTS SIO.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white md:text-center"
              >Creation d'une API afin de recuperer et permettre la creation
              d'un crud sur un format JSON.</span
            >
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Permettre a l'utilisateur de s'inscrire a un seminaire et de
              pouvoir le consulter.
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
                @click="showJSON = !showJSON"
                class="cursor-pointer w-10 h-10"
                src="~/assets/img/json.png"
                alt="json"
              />
              <Transition>
                <span v-if="showJSON" class="text-white text-xl mt-2"
                  >JSON</span
                >
              </Transition>
            </div>
            <div class="flex flex-col items-center"></div>
          </div>
        </div>
      
      </div>
      
    </div>
  </div>
  <div class="mt-10 ml-4 mr-4 md:ml-0 md:mr-0">
    <div
      id="controls-carousel"
      class="w-full relative flex flex-col justify-center items-center"
      data-carousel="static"
    >
      <div class="h-56 overflow-hidden w-[60rem] relative rounded-lg md:h-96">
        <div class="hidden duration-500" data-carousel-item>
          <img
            src="~/assets/img/seminairejson1.png"
            class="w-full md:w-[70rem] absolute block max-w-full mt-10 -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto1"
          />
        </div>
        <div class="hidden duration-500" data-carousel-item="active">
          <img
            src="~/assets/img/seminairejson3.png"
            class="w-96 md:w-[70rem] absolute block max-w-full h-auto mt-10 -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto2"
          />
        </div>
        <div class="hidden duration-500" data-carousel-item="static">
          <img
            src="~/assets/img/seminairejson2.png"
            class="w-96 md:w-[70rem] absolute block max-w-full mt-10 h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto2"
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
</div>

</template>

<script></script>
