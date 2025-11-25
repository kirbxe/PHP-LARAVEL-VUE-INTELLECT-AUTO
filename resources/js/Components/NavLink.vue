<script setup>
import { computed } from "vue";
import { Link } from "@inertiajs/vue3";

const props = defineProps({
    href: {
        type: String,
        required: true,
    },
    active: {
        type: Boolean,
    },
});

const classes = computed(
    () =>
        props.active
            ? "shrink-0 inline-flex items-center text-xs font-normal font-Inter leading-4 text-[#707070] focus:outline-none transition duration-150 ease-in-out" //Статичное
            : "shrink-0 inline-flex items-center text-xs font-normal leading-4 text-gray-500 hover:text-gray-900 focus:outline-none focus:text-gray-700 transition duration-150 ease-in-out" //Активное
);
</script>

<template>
    <Link :href="href" :class="classes">
        <slot />
    </Link>
</template>
