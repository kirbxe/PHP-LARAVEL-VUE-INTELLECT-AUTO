<script setup>
defineProps({
    Price: {
        type: Int16Array,
        required: true,
    },
});
</script>

<template>
    <div class="text-left">{{ Price }}₽</div>
</template>

<style scoped></style>
