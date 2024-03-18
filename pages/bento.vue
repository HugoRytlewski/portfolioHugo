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
    const showNuxt = ref(false);
    const Image = ref(true);
    </script>
    <template>
      <title>Projet Youtube Bento</title>
    
      <div class="flex flex-col min-h-screen">
        <NavbarProjet />
    
        <div class="flex-grow">
          <div class="mt-28 flex flex-col justify-center items-center">
            <img
              class="w-2/5 h-3/6 rounded-xl md:w-auto"
              src="~/assets/img/Youtube_logo.ico "
              alt="youtube-logo"
            />
            <div
              class="mt-10 md:mt-28 w-3/5 border-b-2 pb-4 border-white md:flex justify-between"
            >
              <h1 class="text-4xl text-red-500">Youtube Bento</h1>
              <div class="flex gap-2">
                <a class="text-white text-xl md:text-2xl">Consulter le site </a>
    
                <a
                  class="text-white text-xl md:text-2xl underline underline-offset-8"
                  href="https://youtubebento.vercel.app"
                  target="_blank"
                  >ici
                </a>
                <a
                  class="text-white text-xl md:text-2xl"
                  href="https://feed-beryl.vercel.app"
                  target="_blank"
                  >!
                </a>
              </div>
            </div>
            <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
              <h1 class="text-3xl text-red-500">Résumé</h1>
              <div>
                <span class="text-2xl text-white"
                  >Youtube Bento est un concept Youtube reprenant le Bento Design</span
                >
              </div>
            </div>
            <div class="mt-8 md:mt-10 w-3/5 gap-8 md:flex">
              <h1 class="text-3xl text-red-500">Mission(s)</h1>
              <div class="flex flex-col mt-4 md:mt-0">
                <span class="text-2xl text-white text-left md:text-center"
                  >Reproduire un Design figma et le compléter </span
                >
              </div>
              <br />
              <div class="flex flex-col">
                <span class="text-2xl text-white text-left md:text-center"
                  >Utiliser mes connaissances sur Nuxt pour le développement
                </span>
              </div>
            </div>
            <div class="h-16 mt-8 md:mt-10 w-3/5 gap-10 md:flex ">
              <h1 class="text-3xl text-red-500">Technologies</h1>
              <div
                class="gap-4 mt-5 flex flex-wrap justify-start md:justify-start md:mt-0"
              >
           
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
                <div class="flex flex-col items-center w-10 ">
                    <img
                      @click="ShowCss = !ShowCss"
                      class="cursor-pointer w-10 h-10 "
                      src="~/assets/img/tailwind.png"
                      alt="css"
                    />
                    <Transition>
                      <span v-if="ShowCss" class="text-white text-xl mt-2 ">Tailwind</span>
                    </Transition>
                  </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div></div>
      
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