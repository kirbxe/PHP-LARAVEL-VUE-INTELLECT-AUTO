<script setup>
defineProps({
    LinkSrc: {
        Type: String,
        require: true,
    },
});
</script>

<template>
    <div class="w-full aspect-square relative">
        <img
            :src="LinkSrc"
            alt="Не удалось загрузить изображение"
            class="w-full rounded-[10px] aspect-square object-cover"
        />
    </div>
</template>

<style scoped></style>
