<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>


<template>
    <div class="text-[16px] font-regular font-inter text-[#0075B1] mb-[32px]">{{ text }}</div>
</template>
