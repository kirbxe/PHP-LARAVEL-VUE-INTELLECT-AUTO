<script setup>
defineProps({
    Text: {
        type: String,
        required: true,
    },
    PlaceHolder: {
        type: String,
        required: false,
    },
});
</script>

<template>
    <div class="p-[9px] w-[312px] h-[41px] flex items-start rounded-[4px]">
        <img
            class="size-[24px] absolute my-[9px] ml-[10px]"
            src="/public/image/Search.svg"
            alt="Search"
        />
        <input class="w-full h-auto bg-[#EEEEEE] border-0" type="search" />
    </div>
</template>

<style scoped></style>
