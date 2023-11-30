<script setup lang="ts">
import { ref, onBeforeMount } from 'vue';
import axios from 'axios';
import Profile from './components/Profile.vue';
import NavBar from './components/NavBar.vue';
import Experiencia from './components/Experiencia.vue';
import Proyectos from './components/Proyectos.vue';
import Habilidades from './components/Habilidades.vue';
import Spinnet from './components/Spinnet.vue';

const CargandoExperienfias = ref(true);
const CargandoProjects = ref(true);
const CargandoSkills = ref(true);
const SobreMi = ref({});
const Experiencias = ref([]);
const Projects = ref([]);
const Skills = ref([]);

onBeforeMount(() => {
  axios.get('https://apibckdn.arturozepeda.xyz/about?aboutId=654dbf1f088d780f4aea74f7')
    .then(response => {
      SobreMi.value = response.data;
    })
    .catch(e => console.log(e));
  axios.get('https://apibckdn.arturozepeda.xyz/skills')
    .then(response => {
      Skills.value = response.data;
      CargandoSkills.value = false;
    })
    .catch(e => console.log(e));
  axios.get('https://apibckdn.arturozepeda.xyz/projects')
    .then(response => {
      Projects.value = response.data;
      CargandoProjects.value = false;
    })
    .catch(e => console.log(e));
  axios.get('https://apibckdn.arturozepeda.xyz/experience')
    .then(response => {
      Experiencias.value = response.data;
      CargandoExperienfias.value = false;
    })
});




</script>

<template>
  <div class="fixed w-full">
    <NavBar class="relative"/>
  </div>
  <div>
    <div
      class="banner-personalizado bg-fixed justify-center space-y-15 shadow-lg py-5 bg-gray-600 w-full antialiased colums-1">
      <div id="PROFILE" class="flex justify-center items-center w-full py-10">
        <Profile class="break-after-column w-1/2 content-center" :SobreMi="SobreMi" />
      </div>
      <div class="flex justify-center items-center">
        <div class="bg-white  rounded-lg ficha-inicial w-1/2">
          <!-- This is an example component -->
          <div id="EXPERIENCE" class="max-w-2xl mx-auto py-3">
            <h2 class="text-2xl font-bold text-gray-900">Experience</h2>
            <Spinnet v-if="CargandoExperienfias" class="flex justify-center items-center" />
            <ol class=" border-l border-gray-200 dark:border-gray-700" v-else>
              <Experiencia class="relative  content-center " v-for="Experiencia in Experiencias"
                :Experiencia="Experiencia" />
            </ol>
          </div>
        </div>
      </div>

      <div class="flex justify-center items-center py-10">
        <div id="PORTFOLIO" class="bg-white  rounded-lg ficha-inicial w-1/2">
          <!-- This is an example component -->
          <div class="max-w-2xl mx-auto py-3">
            <h2 class="text-2xl font-bold text-gray-900">Portfolio</h2>
            <Spinnet v-if="CargandoProjects" class="flex justify-center items-center" />
            <div class="columns-2" v-else>
              <Proyectos v-for="project in Projects" :project="project" />
            </div>
          </div>
        </div>
      </div>
      <div class="flex justify-center items-center">
        <div id="ABILITIES" class="bg-white  rounded-lg ficha-inicial w-1/2">
          <!-- This is an example component -->
          <div class="max-w-2xl mx-auto py-3">
            <h2 class="text-2xl font-bold text-gray-900">Technical abilities</h2>
            <Spinnet v-if="CargandoSkills" class="flex justify-center items-center" />
            <div class="columns-2" v-else>
              <Habilidades class="break-inside-avoid-column content-center" v-for="skill in Skills" :skill="skill" />
            </div>
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
  background-blend-mode: normal;
  background-size: cover;
}
</style>
