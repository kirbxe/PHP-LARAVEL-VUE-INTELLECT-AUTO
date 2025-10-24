<script setup>
defineProps({
    rating: {
        Type: String,
        require: true,
    },
});
</script>

<template>
    <div class="flex justify-start"><p v-text="rating"></p></div>
</template>

<style scoped></style>
