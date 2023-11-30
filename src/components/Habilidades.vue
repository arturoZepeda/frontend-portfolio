<script lang="ts" setup>
defineProps({
    skill: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <div  class="break-inside-avoid-column" >
        <div class="max-w-md px-8 bg-blue-300 shadow-lg rounded-lg my-3">
            <div>
                <h2 class="text-gray-800 text-3xl font-semibold">{{ skill.nombre }}</h2>
                <p class="mt-2 text-gray-600">{{ skill.descripcion }}</p>
            </div>
            <div class="flex">
                <div class="flex justify-start mt-4 px-3">
                    Since &nbsp; <a href="#" class="text-xl font-medium text-indigo-500">{{ skill.fechaDesde.substring(0,10) }}</a>
                </div>
                <div class="flex justify-end mt-4 px-3">
                    Mastery &nbsp; <a href="#" class="text-xl font-medium text-indigo-500">{{ skill.porcentaje }}%</a>
                </div>
            </div>
        </div>
    </div>
</template>