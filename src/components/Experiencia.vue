<script lang="ts" setup>
defineProps({
    Experiencia: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <li class="mb-10 ml-4">
        <div
            class="absolute w-3 h-3 bg-gray-200 rounded-full -left-1.5 border border-white dark:border-gray-900 dark:bg-gray-700">

        </div>
        {{ Experiencia.Experiencia }}
        <time class="mb-1 text-sm font-normal leading-none text-gray-400 dark:text-gray-500"> {{ Experiencia.fechaInicio }}
            - {{ Experiencia.fechaFin }} </time>
        <h3 class="text-lg font-semibold text-gray-900 dark:text-black">{{ Experiencia.empresa }}</h3>
        <p class="mb-4 text-base font-normal text-gray-500 dark:text-gray-400">{{ Experiencia.descripcion }}</p>
        <a :href="Experiencia.link" v-if="Experiencia.link"
            class="inline-flex items-center px-4 py-2 text-sm font-medium text-gray-900 bg-white border border-gray-200 rounded-lg hover:bg-gray-100 hover:text-blue-700 focus:z-10 focus:ring-2 focus:ring-blue-700 focus:text-blue-700 dark:bg-gray-800 dark:text-gray-400 dark:border-gray-600 dark:hover:text-white dark:hover:bg-gray-700">Learn
            more <svg class="w-3 h-3 ml-2" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd"
                    d="M12.293 5.293a1 1 0 011.414 0l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-2.293-2.293a1 1 0 010-1.414z"
                    clip-rule="evenodd"></path>
            </svg></a>
    </li>
</template>

<style scoped>
.fichaInicial {

    align-self: center;
}
</style>