<script setup>
defineProps({
    LinkSrc: {
        Type: String,
        require: true,
    },
});
</script>

<template>
    <div class="rounded-[10px] w-[250px] h-[250px] relative">
        <img
            :src="LinkSrc"
            alt="Неудалось загрузить изображение"
            class="w-[250px] h-[250px] object-cover"
        />
    </div>
</template>

<style scoped></style>
