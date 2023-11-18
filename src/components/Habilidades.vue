<script lang="ts" setup>
defineProps({
    skill: {
        type: Object,
        required: true
    }
})
</script>

<template>
    <div class="max-w-md py-2 px-8 bg-blue-300 shadow-lg rounded-lg my-20">
        <div class="flex justify-center md:justify-end ">
        </div>
        <div>
            <h2 class="text-gray-800 text-3xl font-semibold">{{skill.nombre}}</h2>
            <p class="mt-2 text-gray-600">{{skill.descripcion}}</p>
        </div>
        <div class="flex">
            <div class="flex justify-start mt-4 px-3">
                Since <a href="#" class="text-xl font-medium text-indigo-500">{{skill.fechaDesde}}</a>
            </div>
            <div class="flex justify-end mt-4 px-3">
                Mastery <a href="#" class="text-xl font-medium text-indigo-500">{{skill.porcentaje}}%</a>
            </div>
        </div>
    </div>
</template>