<script>
export default {
  data() {
    return {
      textValue: "",
      offsetValue: null,
      alphabet: "abcdefghijklmnñopqrstuvwxyz",
      resultado: "",
    };
  },
  mounted() {},
  methods: {
    codificar: function () {
      const fullAlphabet = this.alphabet + this.alphabet + this.alphabet;
      let cipherText = this.textValue;
      let cipherOffset = this.offsetValue || 0;
      let cipherOffsetResult = cipherOffset % this.alphabet.length;
      let cipherResult = "";

      for (let i = 0; i < cipherText.length; i++) {
        let letter = cipherText[i];
        let upper = letter == letter.toUpperCase();
        letter = letter.toLowerCase();

        let index = this.alphabet.indexOf(letter);
        if (index == -1) {
          cipherResult += letter;
        } else {
          index = index + cipherOffsetResult + this.alphabet.length;
          let nextLetter = fullAlphabet[index];
          if (upper) nextLetter = nextLetter.toUpperCase();
          cipherResult += nextLetter;
        }
      }
      !this.textValue.length
        ? (this.resultado = "Ingresa un texto")
        : (this.resultado = cipherResult);
    },
  },
};
</script>

<template>
  <section
    class="relative overflow-hidden min-h-screen flex items-center justify-center"
  >
    <main>
      <div class="mx-auto max-w-7xl">
        <div class="lg:grid lg:grid-cols-12 lg:gap-8">
          <div
            class="px-4 sm:px-6 sm:text-center md:max-w-2xl md:mx-auto lg:col-span-6 lg:text-left lg:flex lg:items-center"
          >
            <div>
              <h1
                class="mt-4 text-4xl tracking-tight font-extrabold text-white sm:mt-5 sm:leading-none lg:mt-6 lg:text-5xl xl:text-6xl"
              >
                <span class="md:block">Codificador de</span>
                <span class="text-red-400 md:block">Cifrado César</span>
              </h1>
              <p
                class="mt-3 text-base text-gray-300 sm:mt-5 sm:text-xl lg:text-lg xl:text-xl"
              >
                Ingresa el texto a codificar, y el número de posiciones de
                desplazo. El resultado cambiará automaticamente.
              </p>
              <p
                class="mt-8 text-sm text-white uppercase tracking-wide font-semibold sm:mt-10"
              >
                Hecho por
              </p>
              <a
                href="https://github.com/andreyanez"
                target="_blank"
                class="mt-5 w-full sm:mx-auto sm:max-w-lg lg:ml-0 flex text-gray-50 items-center gap-1"
              >
                <svg
                  class="w-5 h-5"
                  fill="currentColor"
                  viewBox="0 0 20 20"
                  aria-hidden="true"
                >
                  <path
                    fill-rule="evenodd"
                    d="M10 0C4.477 0 0 4.484 0 10.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0110 4.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.203 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.942.359.31.678.921.678 1.856 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0020 10.017C20 4.484 15.522 0 10 0z"
                    clip-rule="evenodd"
                  />
                </svg>
                andreyanez
              </a>
            </div>
          </div>
          <div class="mt-16 sm:mt-24 lg:mt-0 lg:col-span-6 self-center">
            <div
              class="bg-white sm:max-w-md sm:w-full sm:mx-auto sm:rounded-lg sm:overflow-hidden"
            >
              <div class="px-4 py-8 sm:px-10">
                <div class="mt-6">
                  <form action="#" method="POST" class="space-y-6">
                    <fieldset class="flex gap-2 items-end">
                      <div class="flex-grow">
                        <label for="texto" class="text-left text-sm block"
                          >Texto a codificar</label
                        >
                        <input
                          id="texto"
                          type="text"
                          name="texto"
                          placeholder="Ejm: Peru"
                          required
                          v-model="textValue"
                          class="block w-full shadow-sm focus:ring-blue-400 focus:border-blue-400 sm:text-sm border-gray-300 rounded-md"
                          @input="codificar"
                        />
                      </div>

                      <div class="w-3/12">
                        <label for="desplazo" class="text-center text-sm block"
                          >Posiciones</label
                        >
                        <input
                          id="desplazo"
                          v-model="offsetValue"
                          type="number"
                          name="desplazo"
                          placeholder="Ejm: 3"
                          required
                          class="block w-full shadow-sm focus:ring-blue-400 focus:border-blue-400 sm:text-sm border-gray-300 rounded-md"
                          onkeypress="return event.charCode >= 48 && event.charCode <= 57"
                          min="0"
                          @input="codificar"
                        />
                      </div>
                    </fieldset>
                    <!-- <transition name="fade"> -->
                    <div
                      class="resultado mx-auto text-center opacity-0 h-0"
                      :class="[
                        !!offsetValue && !!textValue ? 'opacity-100 h-20' : '',
                      ]"
                    >
                      <span class="text-sm">Resultado</span>
                      <div
                        class="block p-4 shadow-sm sm:text-sm border border-red-300 rounded-md"
                        ref="resultado"
                      >
                        {{ resultado }}
                      </div>
                    </div>
                    <!-- </transition> -->
                  </form>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </section>
</template>

<style>
.resultado {
  transition: height 400ms ease;
  min-width: 13rem;
}
</style>
