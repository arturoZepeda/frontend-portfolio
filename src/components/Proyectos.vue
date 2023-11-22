<script setup lang="ts">
defineProps({
    project: {
        type: Object,
        required: true
    }
})
</script>
<template>

    <div :key="proyecto.name" class="group relative py-3 bg-fuchsia-500" v-for="proyecto in project">
        <div>
        <a :href="proyecto.url">
            <span
                class="absolute inset-0 bg-gradient-to-r from-teal-500 to-cyan-600 opacity-50 rounded-lg"></span>
        </a>
        <div
            class="relative h-80 w-full overflow-hidden rounded-lg bg-white sm:aspect-h-1 sm:aspect-w-2 lg:aspect-h-1 lg:aspect-w-1 group-hover:opacity-75 sm:h-128">
            <img :src="proyecto.imagen" :alt="proyecto.imageAlt" class="h-full w-full object-cover object-center" />
        </div>
        <h3 class="mt-6 text-sm text-gray-500">
            <a :href="proyecto.href">
                <span class="absolute inset-0" />
                {{ proyecto.titulo }}
            </a>
        </h3>
        <p class="text-base font-semibold text-gray-900">{{ proyecto.descripcion }}</p>
    </div>
    </div>

</template>