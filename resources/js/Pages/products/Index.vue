<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Product" />

    <AuthenticatedLayout>
        <template #header>
            <h2
                class="text-xl font-semibold leading-tight text-gray-800"
            >
                Product Catalog
            </h2>
        </template>

        <div class="py-12 flex justify-center ">
        <Link :href="route('products.create')"><button class="border p-1 rounded-xl hover:bg-blue-500 border-black">Click for create</button></Link>
        </div>
    </AuthenticatedLayout>
</template>