<script setup lang="ts">


import Navbar from '../components/Layouts/NavBar.vue';
import Navbar2 from '../components/Layouts/NavBarr.vue';
import Footer from '../components/Layouts/Footer.vue';




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
})
}

</script>

<template>
  <head>
    <title>Portfolio Hugo Rytlewski</title>
    <meta name="keywords" content="portfolio étudiant, Hugo Rytlewski, développement web, projets de programmation, conception de sites, optimisation SEO, apprentissage en ligne, compétences techniques, HTML, CSS, JavaScript, réalisations académiques, création de sites web, UX/UI, sites responsives, projets interactifs, référencement en ligne, balises meta, stratégies SEO, intégration web, développement frontend, développement backend, codage propre, résolution de problèmes, accessibilité web, expérience utilisateur, projets personnels, compétences en programmation">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://www.hugorytlewski.com">
    <meta property="og:title" content="Hugo Rytlewski Portfolio">
    <meta property="og:description" content="Portfolio de Hugo Rytlewski.">
  
  </head>
  <Transition >
    <Navbar v-if="y>80" />
    <Navbar2 v-else />
  </Transition>

  <div
    class="scroll-container mt-16"
    id="propos"
    
  >
  </div>
  
  <div
    class="anchor"
  >
  <div>

    <div class=" static  mt-10 flex justify-center  h-screen items-center sm:ml-16">
      <div class="text-center  rounded-b-lg flex-col items-center  test  ">

    <p class="w-0 overflow-auto text-left  text-cyan-400 line1 whitespace-pre-line sizefont ">
      $ Bonjour, <span class="cursor1">_</span>
    </p>
    <br>
    <p class="w-0 overflow-auto text-left  text-green-400 line2 whitespace-normal sizefont">
      Je m'appelle Hugo Rytlewski et j'ai 18 ans.<span class="cursor2">_</span>
    </p>
    <br>
    <p class="w-0 overflow-auto text-left  text-rose-600 line3 whitespace-normal sizefont">
      Passionné par l'informatique je me suis orienté vers le BTS SIO au lycée Suzanne Valadon, je suis actuellement en première année<span class="cursor3">_</span>
    </p>
    <br>
    <p class="w-0 overflow-auto text-left  text-white line4 whitespace-normal sizefont">
      Je voudrais poursuivre mes études en licence pro en alternance afin d'obtenir de l'expérience dans le monde du travail et une certaine maîtrise du développement web<span class="cursor4">_</span>
    </p>
    <br>
    <p class="w-0 overflow-auto text-left text-green-400 line5 whitespace-normal sizefont">
      Mon objectif serait de devenir un développeur full stack<span class="cursor5">_</span>
    </p>
  </div>
  
</div>
  </div>
  </div>
  
  <div
    class="scroll-container"
    id="competence"
  >
  </div>
  <div>
    <div class="h-1">
      <Transition   name="fade">

    <h1
      v-if="y>500"
      class=" hidden teest md:flex justify-center text-green-400  text-4xl md:text-6xl"
    >
      $ Mes Compétences_
    </h1>
  </Transition>
  <Transition   name="fade">

<h1
  v-if="y>300"
  class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl"
>
$ Mes Compétences_

</h1>
</Transition>
</div>

    <swiper
      :effect="'cards'"
      :grab-cursor="true"
      :modules="modules"
      class="mt-28  w-3/6 h-80 md:w-1/4 md:h-96"
    >
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
  <div
    id="projets"
  >
  </div>
  <div 
  class="mt-36  md:mt-60"
    ref="test"
  >
  
<div class="h-1">
      <Transition   name="fade">
    <h1
      v-if="y>1200"
      class="hidden teest md:flex justify-center text-green-400 	  text-4xl md:text-6xl"
    >
      $ Mes projets_
    </h1>
  </Transition>
  <Transition   name="fade">

<h1
  v-if="y>900"
  class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl"
>
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
            class="w-20 h-15"
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
  </div>
  <div
    id="contact"
    class="scroll-contact"
  >
  </div>
  

  <div 
    class="mt-36  md:mt-60"
  >
     <div class="h-1">
      <Transition   name="fade">

    <h1
      v-if="y>1900"
      class="hidden teest md:flex justify-center text-green-400  text-4xl md:text-6xl"
    >
      $ Contact

    </h1>
  </Transition>
  <Transition   name="fade">

<h1
  v-if="y>1700"
  class=" teest md:hidden flex justify-center text-green-400  text-4xl md:text-6xl"
>
  $ Contact

</h1>
</Transition>
</div>
    
    <section class="">
  <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
    <div class="py-8 lg:py-16 px-4 mx-auto max-w-screen-md">
      <form action="https://formsubmit.co/hugorytlewski10@gmail.com" method="post" class=" md:space-y-8">
        <div>
          <input type="hidden" name="_captcha" value="false">
          <input type="hidden" name="_next"  value="https://portfolio2-0-sand.vercel.app/accueil#contact">


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
</section>
</div>
<Footer/>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');



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

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 100;
  transform: translateX(-50%);
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
.line1 {
  -webkit-animation: type .4s 1s steps(20, end) forwards;

}

.cursor1 {
  -webkit-animation: blink 1s 1s 2 forwards;
}

.line2 {
  -webkit-animation: type .4s 1.5s steps(20, end) forwards;
}
.cursor2 {
  -webkit-animation: blink 1s 1.5s 2 forwards;

}
.line3 {
  -webkit-animation: type .4s 2s steps(20, end) forwards;
}
.cursor3 {
  -webkit-animation: blink 1s 2s 2 forwards;
}
.line4 {
  -webkit-animation: type .4s 2.5s steps(20, end) forwards;
}
.cursor4 {
  -webkit-animation: blink 1s 2.5s forwards;
}
.line5 {
  -webkit-animation: type .4s 3.5s steps(20, end) forwards;
}
.cursor5 {
  -webkit-animation: blink 1s 3.5s infinite;
}

@-webkit-keyframes blink {
  0% {
    opacity: 0;
  }
  40% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@keyframes blink {
  0% {
    opacity: 0;
  }
  40% {
    opacity: 0;
  }
  50% {
    opacity: 1;     
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
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