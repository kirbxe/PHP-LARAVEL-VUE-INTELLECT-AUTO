<script setup>
defineProps({
    Title: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <h2 class="font-medium text-3xl font-[IBMPlexSans] text-[#0B0D0D]">
        {{ Title }}
    </h2>
</template>

<style scoped></style>
