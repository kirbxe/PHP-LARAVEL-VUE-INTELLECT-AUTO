<script setup>
import CartButton from "../CartButton.vue";
import NameProduct from "./NameProduct.vue";
import OldPriceProduct from "./OldPriceProduct.vue";
import PriceProduct from "./PriceProduct.vue";
import ProductImage from "./ProductImage.vue";
import Packaging from "./ui/Packaging.vue";

defineProps({
    Image: {
        type: String,
        required: true,
    },
    Name: {
        type: String,
        required: true,
    },
    Price: {
        type: Number,
        required: true,
    },
    PackagingText: {
        type: String,
        required: true,
    },
    OldPrice: {
        type: Number,
        required: true,
    },
    TextButton: {
        type: Number,
        required: true,
    },
});
</script>

<template>
    <div>
        <div class="max-w-max h-auto flex flex-col gap-4 items-start">
            <ProductImage :LinkSrc="Image" />
            <div>
                <NameProduct :NameProduct="Name" />
                <Packaging :Packaging="PackagingText" />
            </div>

            <div class="flex gap-2.5 items-center">
                <PriceProduct :Price="Price" />
                <OldPriceProduct :OldPrice="OldPrice" />
            </div>
            <CartButton :Text="TextButton" />
        </div>
    </div>
</template>
