<script setup lang="ts">
import { ref,onBeforeMount, onMounted } from 'vue';
import Profile from './components/Profile.vue';
import NavBar from './components/NavBar.vue';
import Experiencia from './components/Experiencia.vue';
import Proyectos from './components/Proyectos.vue';
import Habilidades from './components/Habilidades.vue';
import axios from 'axios';


const SobreMi = ref([]);
const Experiencias = ref([]);
const callouts = ref([]);
const Skills = ref([]);
const temp = {
  puesto: 'Desarrollador Web',
  empresa: 'Empresa',
  ubicacion: 'Remoto',
  fechaInicio: '2015',
  fechaFin: 'Presente',
  descripcion: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin nec mi ante. Etiam odio eros, placerat eu metus id, gravida eleifend odio. Vestibulum dapibus pharetra odio, egestas ullamcorper ipsum congue ac. Maecenas viverra tortor eget convallis vestibulum. Donec pulvinar venenatis est, non sollicitudin metus laoreet sed. Fusce tincidunt felis nec neque aliquet porttitor',
  link: 'https://arturozepeda.xyz'
};
for (let i = 0; i < 4; i++) {
  Experiencias.value.push(temp);
}
const temp1 = {
  name: "nombre testnombre test nombre test nombre test v nombre test",
  href: "https://arturozepeda.xyz",
  description: "descripcion descripcion descripcion descripcion descripcion descripcion descripcion descripcion descripcion descripcion descripcion ",
  imageSrc: "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg",
  imageAlt: "test logo"
}
for (let i = 0; i < 7; i++) {
  callouts.value.push(temp1);
}

const temp2 = {
    nombre: "JavaScript",
    porcentaje: 90,
    descripcion: "Lenguaje de programación para la web",
    fechaDesde: "2020-01"
}
for (let i = 0; i < 7; i++) {
  Skills.value.push(temp2);
}
onBeforeMount(() => {
  axios.get('https://apibckdn.arturozepeda.xyz/about?aboutId=654dbf1f088d780f4aea74f7')
  .then(response => {
    SobreMi.value.push(response.data);
  })
  .catch(e => console.log(e));
});

console.log(SobreMi.value);
console.log(Experiencias.value);
</script>

<template>
  <div class="fixed w-full"><NavBar /></div>
  
  <div class="banner-personalizado bg-fixed justify-center space-y-15 shadow-lg py-5 bg-gray-600 w-full antialiased colums-1">
    <div id="PROFILE" class="flex justify-center items-center w-full py-10">
      <Profile class="break-after-column w-1/2 content-center" :SobreMi="SobreMi[0]" />
    </div>
    <div class="flex justify-center items-center">
      <div class="bg-white  rounded-lg ficha-inicial w-1/2">
        <!-- This is an example component -->
        <div id="EXPERIENCE" class="max-w-2xl mx-auto py-3">
          <h2 class="text-2xl font-bold text-gray-900">Experience</h2>
          <ol class="relative border-l border-gray-200 dark:border-gray-700">
            <Experiencia class="break-after-column w-1/2 content-center h-fit" v-for="Experiencia in Experiencias"
              :Experiencia="Experiencia" />
          </ol>
        </div>
      </div>
    </div>

    <div class="flex justify-center items-center py-10">
      <div id="PORTFOLIO" class="bg-white  rounded-lg ficha-inicial w-1/2">
        <!-- This is an example component -->
        <div class="max-w-2xl mx-auto py-3">
          <h2 class="text-2xl font-bold text-gray-900 columns-3">Portfolio</h2>
        <div class="columns-2 ">
          <Proyectos class="break-after-column break-inside-avoid-column content-center " v-for="callout in callouts" :callout="callout" />
        </div>
        </div>
      </div>
    </div>
    <div class="flex justify-center items-center">
      <div id="ABILITIES" class="bg-white  rounded-lg ficha-inicial w-1/2">
        <!-- This is an example component -->
        <div class="max-w-2xl mx-auto py-3">
          <h2 class="text-2xl font-bold text-gray-900">Technical abilities</h2>
        <div class="columns-2">
          <Habilidades class=" break-inside-avoid-column content-center" v-for="skill in Skills" :skill="skill" />
        </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.banner-personalizado {
  background-repeat: no-repat;
  background-image: url(./assets/IMG_2997.jpeg);
  background-blend-mode: multiply;
  background-size: cover;
}
</style>
