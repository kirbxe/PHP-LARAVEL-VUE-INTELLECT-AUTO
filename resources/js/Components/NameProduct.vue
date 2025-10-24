<script setup>
const props = defineProps({
    NameProduct: {
        Type: String,
        required: true,
    },
});
</script>

<template>
    <div class="text-[18px] font-medium align-top h-24 overflow-y-auto">
        {{ NameProduct }}
    </div>
</template>

<style scoped></style>
