<script>
export default {
  methods: {
    toggleMenu() {
      const menuToggleIcon = document.querySelector("#menu-toggle-icon");
      const mobileMenu = document.querySelector("#menu");
      mobileMenu.classList.toggle("activated");
      menuToggleIcon.classList.toggle("activated");
    },
  },
};
</script>
<template>
  <header class="fixed top-0 w-full py-5 z-10">
    <nav
      class="relative max-w-7xl mx-auto flex items-center justify-between px-4 sm:px-6"
      aria-label="Global"
    >
      <div class="flex items-center flex-1">
        <div class="flex items-center justify-between w-full md:w-auto">
          <div class="-mr-2 flex items-center md:hidden">
            <button
              type="button"
              class="bg-gray-800 rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:bg-gray-700 focus:outline-none focus:ring-2 focus-ring-inset focus:ring-white"
              aria-expanded="false"
              @click="toggleMenu"
            >
              <span class="sr-only">Open main menu</span>
              <svg
                class="h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                aria-hidden="true"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16"
                />
              </svg>
            </button>
          </div>
        </div>
        <div class="hidden space-x-10 md:flex">
          <nuxt-link to="/" class="font-medium text-white hover:text-gray-300"
            >App</nuxt-link
          >

          <nuxt-link
            to="aboutcaesar"
            class="font-medium text-white hover:text-gray-300"
            >Sobre el Cifrado Cesar</nuxt-link
          >

          <span
            class="font-medium text-white hover:text-gray-300 cursor-pointer"
            @click="$emit('toggleModal')"
            >Herramientas Implementadas</span
          >
        </div>
      </div>
    </nav>

    <!--
				Mobile menu
				-->
    <div
      class="absolute z-10 top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden"
      id="menu"
    >
      <div
        class="rounded-lg shadow-md bg-white ring-1 ring-black ring-opacity-5 overflow-hidden"
      >
        <div class="px-5 pt-4 flex items-center justify-between">
          <div class="-mr-2">
            <button
              type="button"
              @click="toggleMenu"
              id="menu-toggle-icon"
              class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
            >
              <span class="sr-only">Close menu</span>
              <svg
                class="h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                aria-hidden="true"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
          </div>
        </div>
        <div class="px-2 pt-2 pb-3 space-y-1">
          <nuxt-link
            to="/"
            class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50"
            >App</nuxt-link
          >

          <nuxt-link
            to="aboutcaesar"
            class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50"
            >Cifrado Cesar</nuxt-link
          >
        </div>
      </div>
    </div>
  </header>
</template>

<style>
#menu {
  transform: translateY(-100%);
  transition: all 400ms ease;
}
#menu.activated {
  transform: translateX(0%);
}
</style>
