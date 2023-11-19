<script lang="ts" setup>
defineProps({
  SobreMi: {
        type: Object,
        required: true
    }
})

</script>

<template>
  <div class="bg-slate-500 space-x-12 rounded-lg ficha-inicial w-1/2">
    <div
      class=" bg-fixed justify-center space-x-12 space-y-36 shadow-lg  w-full flex flex-row flex-wrap p-3 antialiased">
      <div class="columns-2  rounded-lg">
        <div>
          <img class="rounded-lg shadow-lg imagen-principal" src="../assets/IMG_3165.jpg">
        </div>
        <div>
          <div class="w-full text-left text-white font-semibold relative pt-0 md:pt-0 align-content:center">
            <h1 class="text-4xl font-medium text-white">{{ SobreMi.nombre + " " + SobreMi.apellido }},<span class="font-light text-white">30</span></h1>
            <p class="mt-8 text-white"> <span v-for="titulo in SobreMi.titulo">{{ titulo + " | "}}</span></p>
            <p class="mt-2 text-white">Universidad tecnologica de México</p>
            <p class="font-light text-white mt-3">CDMX, México</p>
            <p class="font-light text-white mt-3">Correo: {{ SobreMi.correo }}</p>
            <p class="font-light text-white mt-3">{{ SobreMi.descripcion }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.fichaInicial {

  align-self: center;
}

.imagen-principal {
  height: 20rem;
  width: 20rem;
  object-fit: cover;
  object-position: right;
  align-content: right;
}
</style>
