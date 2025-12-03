<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>


<template>
    <div class="text-[36px] font-medium font-inter text-[#000000] mb-[1rem] leading-[44px]">{{ text }}</div>
</template>
