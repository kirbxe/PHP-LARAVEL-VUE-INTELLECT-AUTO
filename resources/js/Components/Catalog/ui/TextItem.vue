<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <p class="font-[Roboto] text-[16px] text-[#141414]">{{ text }}</p>
</template>

<style scoped></style>
