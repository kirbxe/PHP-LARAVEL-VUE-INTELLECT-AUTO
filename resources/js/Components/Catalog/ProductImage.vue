<script setup>
defineProps({
    LinkSrc: {
        Type: String,
        require: true,
    },
});
</script>

<template>
    <div class="rounded-[10px] w-full aspect-square relative">
        <img
            :src="LinkSrc"
            alt="Неудалось загрузить изображение"
            class="w-full aspect-square object-cover"
        />
    </div>
</template>

<style scoped></style>
