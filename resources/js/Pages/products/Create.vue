<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Create" />

    <AuthenticatedLayout>
        <template #header>
            <h2
                class="text-xl font-semibold leading-tight text-gray-800"
            >
                Create Product
            </h2>
        </template>
        <div class="py-12 flex justify-center ">

          <form action="">

            <div class="space-y-2">
                <Label>Fuck you</Label>
            </div>

          </form>


        </div>
    </AuthenticatedLayout>
</template>