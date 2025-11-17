<template>
    <n-space vertical>
        <n-pagination v-model:page="page" :page-count="100" />
        <n-pagination v-model:page="page" :page-count="100" :page-slot="8" />
        <n-pagination v-model:page="page" :page-count="100" :page-slot="7" />
    </n-space>
</template>

<script setup>
import { ref } from "vue";

const page = ref(2);
</script>
