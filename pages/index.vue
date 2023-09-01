<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
h1 {
  font-family: 'VT323', monospace;
}
div {
  font-family: 'VT323', monospace;
}
body {
  background-color: #0d0d0d;
}
</style>
<script>

export default {
  props: {
    percentageInterval: {
      type: Number,
      default: 1,
    },
  },
  data() {
    return {
      delay: 1000, 
      countdown: 0, 
      countdownInterval: null,
      currentPercentage: 0,
    };
  },
  mounted() {
    this.startCountdown(); 
  },
  beforeDestroy() {
    this.stopCountdown(); 
  },
  computed: {
    countdownPercentage() {
      return Math.floor((this.currentPercentage / 100) * (100 / this.percentageInterval)) * this.percentageInterval; 
    },
  },
  methods: {
    startCountdown() {
      const intervalTime = this.delay / (100 / this.percentageInterval); 
      this.countdownInterval = setInterval(() => {
        this.currentPercentage += this.percentageInterval; 
        if (this.currentPercentage >= 100) {
          this.stopCountdown();
          this.currentPercentage = 100; 
          this.$router.push('/accueil');
        }
      }, intervalTime);
    },
    stopCountdown() {
      clearInterval(this.countdownInterval);
    },
  },
};



</script>
<template>
  <head>
    <title>Portfolio Hugo Rytlewski</title>
    <meta name="keywords" content="portfolio étudiant, Hugo Rytlewski, développement web, projets de programmation, conception de sites, optimisation SEO, apprentissage en ligne, compétences techniques, HTML, CSS, JavaScript, réalisations académiques, création de sites web, UX/UI, sites responsives, projets interactifs, référencement en ligne, balises meta, stratégies SEO, intégration web, développement frontend, développement backend, codage propre, résolution de problèmes, accessibilité web, expérience utilisateur, projets personnels, compétences en programmation">
    <meta property="og:type" content="website">
    <meta name="author" content="Hugo Rytlewski">
    <meta name="copyright" content="Hugo Rytlewski">
    <meta name="description" content="Portfolio Hugo Rytlewski étudiant en BTS SIO.">
    <link rel="icon" type="image/x-icon" href="/favicon.ico">
    <meta property="og:url" content="https://www.hugorytlewski.com">
    <meta property="og:title" content="Hugo Rytlewski Portfolio">
    <meta property="og:description" content="Portfolio de Hugo Rytlewski.">
  </head>
  <div class="ml-8 mr-8 flex flex-col items-center justify-center min-h-screen  gap-16">
    <div class="w-11/12 sm:w-9/12 md:w-8/12 lg:w-6/12 xl:w-4/12">
<div class="flex justify-between mb-1">
  <span class=" text-xl md:text-2xl text-white">Chargement Portfolio Hugo...</span>
  <span class="text-xl md:text-2xl text-white">{{ countdownPercentage.toFixed(0) }}%</span>
</div>
<div class=" rounded-full h-4 bg-gray-700">
  <div class="bg-white h-4 rounded-full" :style="{ width: countdownPercentage + '%', maxWidth: '100%' }"></div>

</div>
</div>

 
  </div>

</template>




