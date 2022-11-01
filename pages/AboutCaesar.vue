<template>
  <div class="overflow-hidden">
    <div class="relative max-w-7xl mx-auto py-32 px-4 sm:px-6 lg:px-8">
      <div
        class="mx-auto text-base max-w-prose lg:grid lg:grid-cols-2 lg:gap-8 lg:max-w-none"
      >
        <div>
          <h2
            class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-red-400 sm:text-4xl"
          >
            Cifrado César
          </h2>
        </div>
      </div>
      <div class="mt-8 lg:grid lg:grid-cols-2 lg:gap-8">
        <div class="relative lg:row-start-1 lg:col-start-2">
          <div class="relative text-base mx-auto max-w-prose lg:max-w-none">
            <figure>
              <div class="aspect-w-12 aspect-h-7 lg:aspect-none">
                <nuxt-img
                  provider="imgix"
                  src="/veHGlVkU4qQ"
                  alt="image of my site"
                  w="1184"
                  h="1376"
                  class="rounded-lg shadow-lg object-cover object-center"
                ></nuxt-img>
              </div>
            </figure>
          </div>
        </div>
        <div class="mt-8 lg:mt-0 text-gray-50">
          <div class="text-base max-w-prose mx-auto lg:max-w-none">
            <p class="text-lg">
              Un cifrado César es una de las técnicas de cifrado más simples y
              conocidas.
            </p>
          </div>
          <div
            class="mt-5 prose prose-indigo mx-auto text-gray-50 lg:max-w-none lg:row-start-1 lg:col-start-1"
          >
            <p>
              Lleva el nombre de Julio César, es uno de los tipos de cifrados
              más antiguos y se basa en el cifrado monoalfabético más simple. Se
              considera un método débil de criptografía, ya que es fácil
              decodificar el mensaje debido a sus técnicas de seguridad mínimas.
            </p>
            <p>
              Por la misma razón, un cifrado César a menudo se incorpora solo en
              partes de otros esquemas de cifrado complejos
            </p>
            <p>Las ventajas de usar un cifrado César incluyen:</p>
            <ul role="list">
              <li>
                Uno de los métodos más fáciles de usar en criptografía y puede
                proporcionar una seguridad mínima a la información.
              </li>
              <li>Uso de solo una tecla breve en todo el proceso</li>
              <li>
                Uno de los mejores métodos para usar si el sistema no puede usar
                ninguna técnica de codificación complicada
              </li>
            </ul>
            <p>Las desventajas de usar un cifrado César incluyen:</p>
            <ul role="list">
              <li>Uso de estructura simple</li>
              <li>Solo puede proporcionar seguridad mínima a la información</li>
              <li>
                La frecuencia del patrón de letras proporciona una gran pista
                para descifrar el mensaje completo.
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
