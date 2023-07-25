<template>
  <ul class="fixed w-screen block  flex test justify-between  max-h-24  text-white z-40 text text-lg top-0 item-center drop-shadown-md p-7">
    <li>
      <NuxtLink to="/accueil#projets">

        <button class="flex items-center justify-center ml-4 ">
          <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
          >
          <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
          />
          </svg>
          <h2 class="sm:block teest text-xl">
            Retour a l'accueil
          </h2>
        </button>
      </NuxtLink>
    
        </li>
   
  </ul>
</template>

<script>
export default {
  data() {
    return {
      isShowDropdown: false,
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
.test {
  background-color: #0d0d0d;
  font-family: 'VT323', monospace;

}
html {
  scroll-behavior: smooth;
}


.h{

  box-shadow: 0 2px 2px 1px rgba(128, 127, 127, 0.2);

}
.teest{
  font-family: 'VT323', monospace;

}

.v-enter-active,
.v-leave-active {
  transition: all 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
  transform: translateX(-100%);
}
</style>
