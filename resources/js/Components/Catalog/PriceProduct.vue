<script setup>
defineProps({
    Price: {
        type: Number,
        required: true,
    },
});
</script>

<template>
    <div class="text-[#313131] text-base font-regular font-inter">
        {{ Price }}₽
    </div>
</template>

<style scoped></style>
