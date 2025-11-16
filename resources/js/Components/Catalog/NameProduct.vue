<script setup>
const props = defineProps({
    NameProduct: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div
        class="text-[14px] font-medium font-[Roboto] color-[#313131] lineClamp"
        :title="NameProduct"
    >
        {{ NameProduct }}
    </div>
</template>

<style scoped>
.lineClamp {
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
</style>
