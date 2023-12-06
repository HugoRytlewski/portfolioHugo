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
const showPhp = ref(false);
</script>
<template>
  <title>Projet Ap Congrès</title>

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img
          class="w-2/5 h-3/6 rounded-xl md:w-auto  "
          src="~/assets/img/analim.ico "
          alt="collection-logo"
        />
        <div
          class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
        >
          <h1 class="text-4xl text-white">Ap Congrès</h1>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >C'est un projet réalisé dans le cadre d'un ap au sein de ma
              formation BTS SIO.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white md:text-center"
              >Permet la création et la modification d'une facture.</span
            >
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Permet a l'utilisateur de consulter le detail d'une facture et de
              l'avoir en format pdf
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
                @click="showPhp = !showPhp"
                class="cursor-pointer w-16 h-10"
                src="~/assets/img/php.png"
                alt="php"
              />
              <Transition>
                <span v-if="showPhp" class="text-white text-xl mt-2">PHP</span>
              </Transition>
            </div>
            <div class="flex flex-col items-center"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="mt-10 md:mt-0 ml-4 mr-4 md:ml-0 md:mr-0">
    <div id="controls-carousel" class=" w-full relative   flex flex-col justify-center items-center " data-carousel="static">
      <div class=" h-56 overflow-hidden w-[60rem]  relative rounded-lg md:h-96">
        <div class="hidden duration-500 " data-carousel-item>
          <img
            src="~/assets/img/facture1.png"
            class="object-center object-cover w-[70rem] absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto1"
          />
        </div>
        <div
          class="hidden duration-500 "
          data-carousel-item="active"
        >
          <img
            src="~/assets/img/facture2.png"
            class="object-center object-cover w-[70rem] absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto2"
          />
        </div>
        <div
          class="hidden duration-500  "
          data-carousel-item="static"
        >
          <img
            src="~/assets/img/facture3.png"
            class="object-center object-cover w-[70rem] absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-resto2"
          />
        </div>
          <div
          class="hidden duration-500  "
          data-carousel-item="static"
        >
          <img
            src="~/assets/img/facture4.png"
            class="object-center object-cover w-[70rem] absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
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
</template>

<script></script>
