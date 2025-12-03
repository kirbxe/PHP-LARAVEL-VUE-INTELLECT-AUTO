<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>


<template>
    <div class="text-[16px] font-regular font-inter text-[#0B0D0D] mb-[16px]">{{ text }}</div>
</template>
