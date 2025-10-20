<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
import CartButton from '@/Components/CartButton.vue';

const props = defineProps({ products: Object })

</script>

<template>

    <Head title="Product" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Product Catalog
            </h2>
        </template>

        <div class='py-12 flex justify-center font-[Roboto]'>
            <Link :href="route('products.create')"><button
                class="border p-1 rounded-xl hover:bg-blue-500 border-black">Click
                for create</button></Link>
        </div>
        <div class='flex justify-center gap-x-[10px] flex-wrap px-12 font-[Roboto]'>
            <div v-for="product in props.products" :key="product.id" class='w-[200px] h-[462px] flex flex-col justify-between border border-[black] mb-1 font-roboto'>
                <div class='rounded-[10px] p-2 w-full h-[270px]'> 
                     <img src="{{ product.pricture1 }}" alt=""> 
                </div>
                <div class="flex justify-start">
                    здесь будет рейтинг
                </div>
                <span class="text-[18px] font-medium">{{ product.name }}</span>
                   <div class='flex justify-between'>
                   <span class='text-left '>{{ product.price }}₽</span> 
                    <CartButton/>
                </div> 
            </div>
        </div>

    </AuthenticatedLayout>
</template>