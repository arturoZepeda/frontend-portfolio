<script setup lang="ts">
defineProps({
    project: {
        type: Object,
        required: true
    }
})
</script>
<template>
    <div :key="project.name" class="group relative">
        <a :href="project.url">
            <span
                class="absolute inset-0 bg-gradient-to-r from-teal-500 to-cyan-600 opacity-50 rounded-lg"></span>
        </a>
        <div
            class="relative h-80 w-full overflow-hidden rounded-lg bg-white sm:aspect-h-1 sm:aspect-w-2 lg:aspect-h-1 lg:aspect-w-1 group-hover:opacity-75 sm:h-128">
            <img :src="project.imagen" :alt="project.imageAlt" class="h-full w-full object-cover object-center" />
        </div>
        <h3 class="mt-6 text-sm text-gray-500">
            <a :href="project.href">
                <span class="absolute inset-0" />
                {{ project.titulo }}
            </a>
        </h3>
        <p class="text-base font-semibold text-gray-900">{{ project.descripcion }}</p>
    </div>
</template>
<style scoped></style>