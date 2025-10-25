<script setup>
defineProps({
    Title: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <h2 class="font-semibold text-4xl font-[Roboto] text-[#141414]">
        {{ Title }}
    </h2>
</template>

<style scoped></style>
