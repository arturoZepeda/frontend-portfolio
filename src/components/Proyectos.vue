<script setup lang="ts">
defineProps({
    project: {
        type: Object,
        required: true
    }
})
</script>
<template>
    <div :key="project.name" class="">
        <div class=" px-8 bg-blue-300 shadow-lg rounded-lg my-3">
            <a :href="project.url">
                <span class=" inset-0 bg-gradient-to-r  opacity-50 rounded-lg"></span>
            </a>
            <div
                class="h-80  rounded-lg bg-white sm:aspect-h-1 sm:aspect-w-2 lg:aspect-h-1 lg:aspect-w-1 group-hover:opacity-75 sm:h-128">
                <img :src="project.imagen ? project.imagen : '../assets/garfield-im-working.gif'" :alt="project.imageAlt"
                    class="h-full w-full object-center" />
                {{ project.imagen + ' ' + project.imageAlt }}
            </div>
            <h3 class="mt-6 text-sm text-gray-500">
                <a :href="project.href">
                    <span class=" inset-0" />
                    {{ project.titulo }}
                </a>
            </h3>
            <p class=" font-semibold text-gray-900">{{ project.descripcion + '' + project.descripcion }}</p>
        </div>
    </div>
</template>