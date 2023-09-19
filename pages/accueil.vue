<script setup>
import Navbar from '../components/Layouts/NavBar.vue';
import Navbar2 from '../components/Layouts/NavBarr.vue';
import Footer from '../components/Layouts/Footer.vue';

const Text1 = ref(false);
const Text2 = ref(true);




import "assets/css/main.css";
import { useWindowScroll } from "@vueuse/core";
const { y } = useWindowScroll();
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/effect-cards";
import { EffectCards } from "swiper";
const modules = [EffectCards];


function scrollToId() {
  window.scrollTo({
    top: 0,
    left: 0,
    behavior: "smooth"
  });
}

const textLines = [
  "$ Bonjour,",
  "Je m'appelle Hugo Rytlewski et j'ai 19 ans_.",
  "Passionné par l'informatique, j'ai choisi le BTS SIO au lycée Suzanne Valadon, où je suis actuellement en deuxième année.",
  "Je voudrais poursuivre mes études en licence pro en alternance afin d'obtenir de l'expérience dans le monde du travail et une certaine maîtrise du développement web_.",
  "Mon objectif est de devenir un développeur full stack_."
];

onMounted(() => {

  if (process.client) {
    const lineElements = document.querySelectorAll('.sizefont');

    function typeText(lineIndex, charIndex) {
      const lineElement = lineElements[lineIndex];
      const text = textLines[lineIndex];
      if (charIndex <= text.length) {
        lineElement.textContent = text.substring(0, charIndex);
        charIndex++;
        requestAnimationFrame(() => {
          typeText(lineIndex, charIndex);
        });
      } else {
        const nextLineIndex = lineIndex + 1;
        if (nextLineIndex < lineElements.length) {
          typeText(nextLineIndex, 0);
        }
      }
    }

    if (lineElements.length > 0) {
      typeText(0, 0);
    }
  }
});
</script>

<template>
  <head>
    <title>Portfolio Hugo Rytlewski</title>
  </head>
  <Transition >
    <Navbar v-if="y>80" />
    <Navbar2 v-else />
  </Transition>
  <div class="scroll-container h-[5vh] xl:h-0 mt-10 xs:mt-16" id="propos">
  </div>
  <div class="anchor ">
    <div>
      <div class="w-[80vw] xs:mt-10 xl:mt-48 flex flex-col justify-start test h-screen ml-10 mr-10 gap-6  xl:ml-52">
        <p class="mt-4 overflow-hidden text-left text-cyan-400  whitespace-normal sizefont"></p>
        <p class=" overflow-hidden text-left text-green-400  whitespace-normal sizefont"></p>
        <p class=" overflow-hidden text-left text-rose-600  whitespace-normal sizefont"></p>
        <p class=" overflow-hidden text-left text-white  whitespace-normal sizefont"></p>
        <p class=" overflow-hidden text-left text-green-400  whitespace-normal sizefont"></p>
      </div>
    </div>
  </div>
  <div class="scroll-container" id="competence">
  </div>
  <div>
    <div class="h-1 mt-10">
      <Transition   name="fade">
        <h1 v-if="y>500" class=" hidden teest md:flex justify-center  text-green-400  text-4xl md:text-6xl">
          $ Mes Compétences_
        </h1>
      </Transition>

      <Transition   name="fade">
        <h1 v-if="y>300" class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl">
        $ Mes Compétences_
        </h1>
      </Transition>
    </div>
    <swiper :effect="'cards'" :grab-cursor="true" :modules="modules" class="mt-28  w-3/6 h-80 md:w-1/4 md:h-96">
      <swiper-slide  >
        <a href="https://nuxt.com/" target="_blank" class="h-full w-full">
        </a>
        <span>Nuxt</span>
      </swiper-slide>
      <swiper-slide>
        <a href="https://tailwindcss.com/" target="_blank" class="h-full w-full">
        </a>
        <span>Tailwind</span>
      </swiper-slide>
      <swiper-slide>
        <a href="https://symfony.com/" target="_blank" class="h-full w-full">
        </a>
        <span>Symfony</span>
      </swiper-slide>
      <swiper-slide>
        <a href="https://github.com/" target="_blank" class="h-full w-full" >
        </a>
        <span>Github</span>
      </swiper-slide>
    </swiper>
  </div>
  <div id="projets">
  </div>
  <div class="mt-36  md:mt-60" ref="test">
    <div class="h-1">
      <Transition   name="fade">
        <h1 v-if="y>1200" class="hidden teest md:flex justify-center text-green-400 	  text-4xl md:text-6xl">
          $ Mes projets_
        </h1>
      </Transition>
      <Transition   name="fade">
        <h1 v-if="y>900" class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl">
          $ Mes projets_
        </h1>
      </Transition>
    </div>
  </div>
  <div class="flex flex-wrap justify-center text-center mt-16 md:mt-20 text-black text-lg font-medium ">
    <div class="p-4"> 
      <nuxt-link to="/projet1">
        <div class=" flex rounded-lg h-full p-20 bg-white flex-col ease-in duration-200    md:hover:-translate-y-1 md:hover:scale-105  hover:ring-4 ring-green-400 md:p-28">
          <div class="flex flex-col justify-between flex-grow">
            <img class="w-20 h-15" src="~/assets/img/logo.png" alt="resto">
          </div>
          <div class="mt-3">
            <h1 class="text-2xl text-black">
              RESTO.FR
            </h1>
          </div>
        </div>
      </nuxt-link>
    </div>
    <div class="p-4">
      <nuxt-link to="/projet2">
        <div class=" flex rounded-lg h-full p-20 bg-white flex-col ease-in duration-200   md:hover:-translate-y-1 md:hover:scale-105  hover:ring-4 ring-green-400 md:p-28">
          <div class="flex flex-col justify-between flex-grow">
            <img
              class="w-20 h-15 "
              src="~/assets/img/icon-nexton.png"
              alt="Nextfeed"
            >
          </div>
          <div class="mt-3">
            <h1 class="text-2xl text-black">
              NEXTFEED
            </h1>
          </div>  
        </div>
      </nuxt-link>
    </div>
    <div class="p-4">
      <nuxt-link to="/projet3">
        <div class=" flex rounded-lg h-full p-20 bg-white   flex-col ease-in duration-200   md:hover:-translate-y-1 md:hover:scale-105  hover:ring-4 ring-green-400 md:p-28">
          <div class="flex flex-col justify-between  items-center justify-center">
            <img
              class="w-20 h-15 rounded-xl "
              src="~/assets/img/meteo.png"
              alt="Météo"
            >
          </div>
          <div class="mt-3">
            <h1 class="textcustom  text-black">
              Météo
            </h1>
          </div>  
        </div>
      </nuxt-link>
    </div>
    <div class="p-4">
      <nuxt-link to="/projet4">
        <div class=" flex rounded-lg h-full p-20 bg-white   flex-col ease-in duration-200   md:hover:-translate-y-1 md:hover:scale-105  hover:ring-4 ring-green-400 md:p-28">
          <div class="flex flex-col justify-between  items-center justify-center">
            <img
              class="w-20 h-15 rounded-xl "
              src="~/assets/img/lettre-f.png"
              alt="Feed"
            >
          </div>
          <div class="mt-3">
            <h1 class="textcustom  text-black">
              Feed 
            </h1>
          </div>  
        </div>
      </nuxt-link>
    </div>
  </div>
  <div id="veille" class="scroll-contact">
  </div>
  <div class="mt-36  md:mt-60">
    <div class="h-1">
      <Transition   name="fade">
        <h1 v-if="y>1800" class="hidden teest md:flex justify-center text-green-400  text-4xl md:text-6xl">
          $ Veille
        </h1>
      </Transition>
      <Transition   name="fade">
        <h1 v-if="y>2400" class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl">
          $ Veille
        </h1>
      </Transition>
    </div>
    <div class="relative flex justify-center mt-40 md:mt-48 xl:mt-24   items-center lg:overflow-hidden">
      <div class=" lg:flex-row items-center bg-white h-[25rem]	 w-[95vw]  lg:h-[30rem] lg:w-[60vw] rounded-xl ">

      <Transition name="slide2">
          <div v-if="Text2 && y>1800" class="absolute  ">

            <div  class=" flex flex-col lg:flex-row items-center   w-[95vw]  lg:h-[30rem] lg:w-[60vw]">

              <div class="hidden lg:block translate-y-[-30%] lg:translate-y-0 lg:translate-x-[-30%]  duration-700  lg:hover:shadow-sm shadow-2xl	 z-10 h-[10rem] w-[80vw]  lg:w-[20vw]  lg:h-[40vh] rounded-xl bg-green-500">
            </div>
            <div  class="flex flex-col mt-[-2rem] lg:mt-0 justify-center h-[30rem] p-3 gap-2 lg:gap-6 lg:w-[35vw] w-[80vw] text-center items-center lg:text-start">
          <p class="text-lg lg:text-xl">Veille Technologique</p>
          <h1 class="text-2xl lg:text-3xl ">C'est quoi ?</h1>
          <p class="lg:text-2xl text-center"> La veille informatique consiste à surveiller, analyser et partager des informations technologiques pour rester compétent et à jour en developpement web et en CyberSécurité.</p>
          <button @click=" Text1= !Text1,Text2 = !Text2" class="bg-green-500 lg:hover:bg-green-700 duration-300 w-48 text-white rounded-xl p-2">En savoir plus</button>
        </div>
      </div>
    </div>

  </Transition>
    <Transition name="slide1">

      <div v-if="Text1 && y>1900" class="absolute ">

        <div  class=" flex flex-col lg:flex-row items-center   w-[95vw]  lg:h-[30rem] lg:w-[60vw]">
          
          <div class="hidden lg:block translate-y-[-30%] lg:translate-y-0 lg:translate-x-[-30%]  duration-700  lg:hover:shadow-sm shadow-2xl	 z-10 h-[10rem] w-[80vw]  lg:w-[20vw]  lg:h-[40vh] rounded-xl bg-green-500">
          </div>
          <div  class="flex flex-col mt-[-2rem] lg:mt-0 justify-center h-[30rem] p-3 gap-2 lg:gap-6 lg:w-[35vw] w-[80vw] text-center items-center lg:text-start">
            <p class="text-lg lg:text-xl">Veille Technologique</p>
            <h1 class="text-2xl lg:text-3xl ">Outil de Veille</h1>
            <p class="lg:text-2xl text-center">Pour ma veille informatique j'utilise l'outil <a class="hover:underline italic" href="/projet4"> Feed Tracker</a>  c'est un outil que j'ai codé et que j'utilise au quotidien, je consulte des flux rss sur la CyberSécurité et le developpement Web.</p>
            <button @click=" Text2= !Text2,Text1 = !Text1" class="bg-green-500 lg:hover:bg-green-700 duration-300 w-48 text-white rounded-xl p-2">En savoir plus</button>
          </div>

        </div>
      </div>

    </Transition>

  </div>

    </div>
  </div>
  <div id="contact" class="scroll-contact">
  </div>
  <div class="mt-36  md:mt-60">
    <div class="h-1">
      <Transition   name="fade">
        <h1 v-if="y>2700" class="hidden teest md:flex justify-center text-green-400  text-4xl md:text-6xl">
          $ Contact
        </h1>
      </Transition>
      <Transition   name="fade">
        <h1 v-if="y>2900" class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl">
          $ Contact
        </h1>
      </Transition>
    </div>
    <div class="">
      <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
        <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
          <form action="https://formsubmit.co/hugorytlewski10@gmail.com" method="post" class=" md:space-y-8">
            <div>
              <input type="hidden" name="_captcha" value="false">
              <input type="hidden" name="_next"  value="https://hugorytlewski.com/accueil#contact">
              <label for="email" class="block mb-2 text-2xl text-white">Mail</label>
              <input type="email" name="email" id="email" class="shadow-sm border border-gray-300 text-gray-900 text-xl rounded-lg focus:ring-primary-500 focus:border-primary-500 block w-full p-2.5 bg-white border-gray-600 placeholder-gray-400 text-black focus:ring-primary-500 focus:border-primary-500 shadow-sm-light" placeholder="hugorytlewski10@gmail.com" required>
            </div>
            <div>
              <label for="subject" class="block mb-2 text-2xl text-white">Nom</label>
              <input type="text" name="name" id="subject" class="block p-3 w-full text-xl text-gray-900 rounded-lg border border-gray-300 shadow-sm focus:ring-primary-500 focus:border-primary-500 bg-white border-gray-600 placeholder-gray-400 text-black focus:ring-primary-500 focus:border-primary-500 shadow-sm-light" placeholder="Hugo" required>
            </div>
            <div class="sm:col-span-2">
              <label for="message" class="block mb-2 text-2xl text-white">Message</label>
              <textarea id="message" name="msg" rows="6" class="block p-2.5 w-full text-xl text-black rounded-lg shadow-sm border border-gray-300 focus:ring-primary-500 focus:border-primary-500 bg-white border-gray-600 placeholder-gray-400 text-black text-xl focus:ring-primary-500 focus:border-primary-500" placeholder="Laisse un message..."></textarea>
            </div>
            <button type="submit" class="py-3 px-5 text-2xl text-center text-white rounded-lg bg-primary-700 sm:w-fit hover:bg-primary-800 focus:ring-4 focus:outline-none focus:ring-primary-300 bg-primary-600 hover:bg-primary-700 focus:ring-primary-800">Envoyer</button>
          </form>
        </div>
      </div>
    </div>
  </div>   
  <Footer/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');


.textcustom{

  font-size: 1.35rem; /* 24px */
line-height: 2rem; /* 32px */
}

@media (min-width: 640px){
  .sizefont {
    font-size: 1.875rem; /* 30px */
    line-height: 2.25rem; /* 36px */

  }
}
@media (max-width: 640px){
  .sizefont {
 font-size: 1.58rem; /* 24px */
line-height: 1.5rem; /* 32px */

  }
}
@media (min-width: 280px){
  .test {
height: 40rem;
}
}
@media (max-width: 280px){
  .test {
height: 37rem;
}
  .sizefont {
 font-size: 1.40rem; /* 24px */
line-height: 1.5rem; /* 32px */

  }
}


@media (min-width: 1024px) {
  .slide2-enter-active,
.slide2-leave-active {
  transition: all 0.5s ease;
}
.slide2-enter-from,
.slide2-leave-to {
 transform: translateY(100%); /* L'élément sortant va vers la gauche */
  opacity: 100;
  opacity: 0;
}

.slide1-enter-active,
.slide1-leave-active {
  transition: all 0.5s ease;
}
.slide1-enter-from,
.slide1-leave-to {
  transform: translateY(-100%); /* L'élément sortant va vers la gauche */
  opacity: 100;
  opacity: 0;
}
}
@media (max-width: 1024px) {

  .slide2-enter-active,
.slide2-leave-active {
  transition: all 0.6s ease;
}
.slide2-enter-from,
.slide2-leave-to {
  transform: translateX(-100%); /* L'élément sortant va vers la gauche */
  opacity: 100;
  opacity: 0;
}

.slide1-enter-active,
.slide1-leave-active {
  transition: all 0.6s ease;
}
.slide1-enter-from,
.slide1-leave-to {
  transform: translateX(-100%); /* L'élément sortant va vers la gauche */
  opacity: 100;
  opacity: 0;
}

}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 100;
  transform: translate(-50%);
  opacity: 0;
}
.scroll-container {
  scroll-margin-top: 170px; /* Remplacez la valeur par l'offset souhaité */
}
.scroll-contact {
  scroll-margin-top: -40px; /* Remplacez la valeur par l'offset souhaité */
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
html {
  scroll-behavior: smooth;
}

body {
  background-color: #0d0d0d;
  font-family: 'VT323', monospace;

}
p {
  font-family: 'VT323', monospace;
}
label {
  font-family: 'VT323', monospace;
}


.teest{
  font-family: 'VT323', monospace;
  font-weight: lighter;

}

@media (min-width: 1024px) { @keyframes type {
  to {
    width: 80vw;
 

  }
} }
@media (max-width: 1024px) { @keyframes type {
  to {
    width: 80vw;


  }
} }


</style>