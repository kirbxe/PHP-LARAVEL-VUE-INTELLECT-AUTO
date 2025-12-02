<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <p class="font-inter text-[12px] text-[#707070] min-w-max h-auto mb-[12px] cursor-pointer">{{ text }}</p>
</template>

<style scoped></style>
