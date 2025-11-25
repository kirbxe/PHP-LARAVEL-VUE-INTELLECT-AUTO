<script setup>
defineProps({
    Packaging: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div>
        <p class="text-[#929292] text-xs font-regular font-inter">
            {{ Packaging }}
        </p>
    </div>
</template>

<style scoped></style>
