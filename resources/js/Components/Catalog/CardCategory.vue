<script setup>
defineProps({
    text: {
        type: String,
        required: true,
    },
});
</script>


<template>
    <div class="text-[16px] font-inter font-regular text-[#707070]">{{ text }}</div>
</template>
