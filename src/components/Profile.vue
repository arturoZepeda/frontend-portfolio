<script setup lang="ts">
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
            <h1 class="text-4xl font-medium text-white">Arturo Zepeda, <span class="font-light text-white">30</span></h1>
            <p class="mt-8 text-white">Software Engineer | Web Developer | EDI Consultant </p>
            <p class="mt-2 text-white">Universidad tecnologica de México</p>
            <p class="font-light text-white mt-3">CDMX, México</p>
            <p class="font-light text-white mt-3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis labore doloremque rerum, impedit alias aliquam autem explicabo voluptate sequi numquam, repellat deserunt eius optio ea. Deserunt vitae harum alias eius!</p>
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
