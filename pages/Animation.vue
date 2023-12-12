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
const ShowCss = ref(false);
</script>
<template>
  <title>Projet Collection</title>

  <div class="flex flex-col min-h-screen">
    <NavbarProjet />

    <div class="flex-grow">
      <div class="mt-28 flex flex-col justify-center items-center">
        <img
          class="w-2/5 h-3/6 rounded-xl md:w-auto"
          src="~/assets/img/lettre-c.ico "
          alt="collection-logo"
        />

        <div
          class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
        >
          <h1 class="text-4xl text-white">Collection</h1>

          <div class="flex gap-2">
            <a class="text-white text-xl md:text-2xl" href=""
              >Consulter le site
            </a>

            <a
              class="text-white text-xl md:text-2xl underline underline-offset-8"
              href="https://animationtest.vercel.app"
              target="_blank"
              >ici
            </a>
            <a
              class="text-white text-xl md:text-2xl"
              href="https://animationtest.vercel.app"
              target="_blank"
              >!
            </a>
          </div>
          <div class="md:flex">
            <p class="text-2xl text-white">Doc Dispo :</p>
            <a
              class="text-white"
              href="https://docs.google.com/document/d/18czweIjmIQo6o6bZsCRto4hvwDxhhAtmpgIV2cKXuT0/edit?usp=sharing"
              target="_blank"
              ><img class="h-10" src="~/assets/img/doc.png" alt=""
            /></a>
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Résumé</h1>
          <div>
            <span class="text-2xl text-white"
              >Collection est un projet personnel qui montre la réalisation d'un
              site de mise en avant d'une collection.</span
            >
          </div>
        </div>
        <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
          <h1 class="text-3xl text-white">Mission(s)</h1>
          <div class="flex flex-col mt-4 md:mt-0">
            <span class="text-2xl text-white text-left md:text-center"
              >Ajout de photos de la collection : elle permet à l'utilisateur de
              visualiser la collection.</span
            >
          </div>
          <br />
          <div class="flex flex-col">
            <span class="text-2xl text-white text-left md:text-center"
              >Ajout d'animation sur la première page : cela permet à
              l'utilisateur d'avoir une meilleure expérience sur le site.
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
            <div class="flex flex-col items-center"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="mt-24 xl:mt-10 ml-4 mr-4 md:ml-0 md:mr-0">
    <div id="controls-carousel" class="relative w-full" data-carousel="static">
      <div class="relative h-56 overflow-hidden rounded-lg md:h-96">
        <div class="hidden duration-300 ease-in-out" data-carousel-item>
          <img
            src="~/assets/img/collection2.png"
            class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-collection"
          />
        </div>
        <div
          class="hidden duration-300 ease-in-out"
          data-carousel-item="active"
        >
          <img
            src="~/assets/img/collection.png"
            class="absolute block max-w-full h-auto -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2"
            alt="screen-collection"
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
