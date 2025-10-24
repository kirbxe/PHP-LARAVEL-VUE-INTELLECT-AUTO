<script setup>
defineProps({
    LinkSrc: {
        Type: String,
        require: true,
    },
});
</script>

<template>
    <div class="rounded-[10px] w-full h-[270px] relative">
        <img
            :src="LinkSrc"
            alt="Неудалось загрузить изображение"
            class="w-[212px] h-[270px] object-fill"
        />
        <div
            class="absolute bottom-2 left-2 w-12 h-6 bg-black text-white flex justify-center rounded-[4px]"
        >
            -33%
        </div>
    </div>
</template>

<style scoped></style>
