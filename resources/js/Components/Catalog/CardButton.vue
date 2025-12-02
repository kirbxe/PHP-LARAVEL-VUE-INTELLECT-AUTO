<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <button class="mt-[32px] bg-[#0075B1] w-[186px] h-[48px] rounded-[10px]">
        <a
            class=" text-white text-[18px] font-medium font-inter"
        >
            {{ text }}
        </a>
    </button>
</template>

<style scoped></style>