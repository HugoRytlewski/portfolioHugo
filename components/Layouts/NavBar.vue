<template>
  <ul class="fixed w-screen block flex justify-between bg-neutral-950 h text-white z-40 text text-lg top-0 item-center drop-shadown-md p-7">
    <li>
      <NuxtLink to="/accueil#propos">
        <button class="flex items-center justify-center ml-4 ">
          <h2 class="sm:block teest text-2xl">
            Hugo Rytlewski
          </h2>
        </button>
      </NuxtLink>
    </li>
    <button
      @click="isShowDropdown = !isShowDropdown"
      class="lg:hidden"
    >
      <svg
        v-if="!isShowDropdown"
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
          d="M4 6h16M4 12h16M4 18h16"
        />
      </svg>
      <svg
        v-else
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
          d="M6 18L18 6M6 6l12 12"
        />
      </svg>
    </button>
    <Transition>
      <div
        v-if="isShowDropdown"
        class=" bg-neutral-950 fixed mt-10 h-screen w-screen  flex-col items-center rounded right-0 p-6 flex  justify-start gap-y-5 "
      >
        <li>
          <button>
            <span class="text-items hover:text-neutral-400">
              <h2
                class="teest text-xl "
              >
                <a
                  href="#propos"
                  @click="isShowDropdown=!isShowDropdown"
                >
                  A propos

                </a>
              </h2>
            </span>
          </button>
        </li>
        <li>
          <button>
            <span class="text-items hover:text-neutral-400">
              <h2 class="teest text-xl">
                <a
                  href="#competence"
                  @click="isShowDropdown=!isShowDropdown"

                >
                  Compétences
                </a>

              </h2>
            </span>
          </button>
        </li>
        <li>
          <button>
            <span class="text-items hover:text-neutral-400">
              <h2 class="teest text-xl">
                <a
                  href="#projets"
                  @click="isShowDropdown=!isShowDropdown"

                >
                  Mes projets

                </a>
              </h2>

            </span>
          </button>
        </li>
        <li>
          <button>
            <span class=" hover:text-neutral-400">
              <h2 class="teest text-xl">
                <a
                  href="#contact"
                  @click="isShowDropdown=!isShowDropdown"

                >
                  Contact

                </a>

              </h2>
            </span>
          </button>
        </li>
      </div>
    </Transition>
    <div
      class="gap-x-8    items-center rounded right-0 flex justify-center hidden lg:flex block "
    >
      <li>
        <button>
          <span class="text-items hover:text-neutral-400">
            <h2 class="teest text-xl">
              <a
                href="#propos"
              >
                A propos

              </a>
            </h2>
          </span>
        </button>
      </li>
      <li>
        <button>
          <span class="text-items hover:text-neutral-400">
            <h2 class="teest text-xl">

              <a
                href="#competence"
              >
                Compétences

              </a>
            </h2>
          </span>
        </button>
      </li>
      <li>
        <button>
          <span class="text-items hover:text-neutral-400">
            <h2 class="teest text-xl">
              <a
                href="#projets"
              >
                Mes projets

              </a>
            </h2>
          </span>
        </button>
      </li>
      <li>
        <button>
          <span class="text-items hover:text-neutral-400">
            <h2 class="teest text-xl">
              <a
                href="#contact"
              >
                Contact

              </a>

            </h2>
          </span>
        </button>
      </li>
    </div>
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
  transform: translateY(-100%);
}
</style>
