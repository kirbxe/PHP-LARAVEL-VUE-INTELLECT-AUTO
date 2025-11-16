<script setup>
defineProps({
    OldPrice: {
        type: Number,
        required: true,
    },
});
</script>

<template>
    <div class="text-[#707070] line-through text-xs font-medium font-roboto">
        {{ OldPrice }}0₽
    </div>
</template>

<style scoped></style>
