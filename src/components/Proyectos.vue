<script setup lang="ts">
defineProps({
    callout: {
        type: Object,
        required: true
    }
})
</script>
<template>
    <div :key="callout.name" class="group relative">
        <div
            class="relative h-80 w-full overflow-hidden rounded-lg bg-white sm:aspect-h-1 sm:aspect-w-2 lg:aspect-h-1 lg:aspect-w-1 group-hover:opacity-75 sm:h-128">
            <img :src="callout.imageSrc" :alt="callout.imageAlt" class="h-full w-full object-cover object-center" />
        </div>
        <h3 class="mt-6 text-sm text-gray-500">
            <a :href="callout.href">
                <span class="absolute inset-0" />
                {{ callout.name }}
            </a>
        </h3>
        <p class="text-base font-semibold text-gray-900">{{ callout.description }}</p>
    </div>
</template>
<style scoped></style>