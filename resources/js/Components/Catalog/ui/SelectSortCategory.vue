<script setup>
defineProps({
    Text: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <div class="w-[312px] h-[24px] flex justify-between flex-row items-center">
        <p class="font-[Roboto] font-medium">{{ Text }}</p>
        <img
            class="size-[15px] color-[#141414] font-[1.2px]"
            src="/public/image/Vector.svg"
            alt="asd"
        />
    </div>
</template>

<style scoped></style>
