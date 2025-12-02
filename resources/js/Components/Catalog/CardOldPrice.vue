<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>


<template>
    <div class="text-[20px] text-[#929292] line-through font-medium font-inter ml-[32px]">{{ text }}</div>
</template>
