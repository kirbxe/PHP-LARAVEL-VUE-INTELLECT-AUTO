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
        <p class="text-[#929292] text-xs font-normal font-roboto">
            {{ Packaging }}
        </p>
    </div>
</template>

<style scoped></style>
