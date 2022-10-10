<script>
export default {
  data() {
    return {
      isModalShowed: false,
    };
  },
};
</script>

<template>
  <div class="app bg-gray-800">
    <HeaderComponent @toggleModal="isModalShowed = !isModalShowed" />
    <nuxt />
    <div
      class="fixed z-10 inset-0 overflow-y-auto"
      :class="[isModalShowed ? 'block' : 'hidden']"
      aria-labelledby="modal-title"
      role="dialog"
      aria-modal="true"
    >
      <div
        class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0"
      >
        <div
          class="fixed inset-0 bg-gray-500 bg-opacity-75 transition-opacity"
          aria-hidden="true"
          @click="isModalShowed = !isModalShowed"
        ></div>
        <span
          class="hidden sm:inline-block sm:align-middle sm:h-screen"
          aria-hidden="true"
          >&#8203;</span
        >
        <div
          class="relative inline-block align-bottom bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-lg sm:w-full sm:p-6"
        >
          <div>
            <div class="mt-3 text-center sm:mt-5">
              <h3
                class="text-lg leading-6 font-medium text-gray-900"
                id="modal-title"
              >
                Tismart-caesar-test v1.0
              </h3>
              <div class="mt-2">
                <p class="text-sm text-gray-500">Hecho con:</p>
              </div>
              <ul role="list" class="flex justify-evenly my-10">
                <li class="text-green-500">Nuxt 2</li>
                <li class="text-green-900">create-nuxt-app</li>
                <li class="text-blue-400">TailwindCSS</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition-property: opacity;
  transition-timing-function: ease-in-out;
  transition-duration: 200ms;
}

.page-enter,
.page-leave-to {
  opacity: 0;
}
</style>
