<script setup>
defineProps({
    Text: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <button class="w-auto h-auto">
        <a
            class="bg-[#0075B1] py-2 px-9 w-max rounded-md text-white text-sm font-regular font-inter"
        >
            {{ Text }}
        </a>
    </button>
</template>

<style scoped></style>
