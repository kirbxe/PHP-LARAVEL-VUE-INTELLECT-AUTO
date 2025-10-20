<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
import CartButton from '@/Components/CartButton.vue';
import { computed } from 'vue';

const props = defineProps({ products: Object })

const pageKey = computed(() => props.products.current_page)
</script>

<template>
    <AuthenticatedLayout>
        <Head title="Product" />
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Product Catalog
            </h2>
        </template>
        <div :key="pageKey">
            <div class='py-12 flex justify-center font-[Roboto]'>
                <Link :href="route('products.create')"><button
                    class="border p-1 rounded-xl hover:bg-blue-500 border-black">Click
                    for create</button></Link>
            </div>
            <div class='grid grid-rows-2 grid-cols-5 gap-y-[10px]  gap-x-[10px] px-12 font-[Roboto]'>
                <div v-for="product in props.products.data" :key="product.id"
                    class='w-[200px] h-[462px] flex flex-col justify-between mb-1 font-roboto'>
                    <div class='rounded-[10px] p-2 w-full h-[270px]'>
                        <img :src="product.picture1" alt="Неудалось загрузить изображение"> 
                    </div>
                    <div class="flex justify-start">
                        здесь будет рейтинг
                    </div>
                    <span class="text-[18px] font-medium">{{ product.name }}</span>
                    <div class='flex justify-between'>
                        <span class='text-left '>{{ product.price }}₽</span>
                        <CartButton />
                    </div>

                </div>

            </div>
            <div class='flex flex-col justify-center'>
                <div class='flex justify-center items-center mt-8 font-[Roboto]'>
                    Показано {{ props.products.from }} по {{ props.products.to }} из {{ props.products.total }}
                </div>
                <div class='flex gap-2 justify-center'>
                    <Link v-if="props.products.prev_page_url" :href="props.products.prev_page_url"
                        class='px-4 py-4 border rounded-md border-[black] hover:bg-gray-300'>
                    Назад
                    </Link>
                    <Link v-if="props.products.next_page_url" :href="props.products.next_page_url"
                        class='px-4 py-4 border rounded-md border-[black] hover:bg-gray-300'>
                    Вперед
                    </Link>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>