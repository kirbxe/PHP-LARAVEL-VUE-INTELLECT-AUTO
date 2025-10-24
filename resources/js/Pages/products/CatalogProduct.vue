<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import CartButton from "@/Components/CartButton.vue";
import { computed } from "vue";
import SortBlock from "../../Components/SortBlock.vue";
import Catalog from "../../Components/Catalog.vue";
import TitleItem from "@/ui/TitleItem.vue";
import SelectSortCategory from "@/ui/SelectSortCategory.vue";
import Search from "@/ui/Search.vue";
import ProductImage from "@/Components/ProductImage.vue";
import RatingProduct from "@/Components/RatingProduct.vue";
import NameProduct from "@/Components/NameProduct.vue";
import PriceProduct from "@/Components/PriceProduct.vue";

const props = defineProps({ products: Object });

const pageKey = computed(() => props.products.current_page);
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
            <div class="py-12 flex justify-center font-[Roboto]">
                <Link :href="route('products.create')"
                    ><button
                        class="border p-1 rounded-xl hover:bg-blue-500 border-black"
                    >
                        Click for create
                    </button></Link
                >
            </div>
            <div class="py-12 flex justify-center bg-white">
                <div class="mx-14 my-6 flex">
                    <SortBlock>
                        <TitleItem Title="Предохранители" class="mb-12" />
                        <SelectSortCategory
                            Text="Поиск с полем ввода"
                            class="mb-6"
                        />
                        <Search />
                    </SortBlock>
                    <Catalog>
                        <div
                            v-for="product in props.products.data"
                            :key="product.id"
                            class="w-[200px] h-[470px] flex flex-col justify-between mb-1 font-roboto"
                        >
                            <div class="w-auto flex flex-col gap-4">
                                <ProductImage :LinkSrc="product.picture1" />
                                <RatingProduct rating="Рейтинг?" />
                                <NameProduct :NameProduct="product.name" />
                            </div>
                            <!-- Не хватает поля -->
                            <div class="flex justify-between">
                                <div class="flex items-end">
                                    <PriceProduct
                                        :Price="product.price"
                                        class="mr-2"
                                    />
                                    <PriceProduct
                                        :Price="product.price"
                                        class="text-gray-400 line-through"
                                    />
                                </div>
                                <CartButton />
                            </div>
                        </div>
                    </Catalog>
                </div>
            </div>

            <div class="flex flex-col justify-center">
                <div
                    class="flex justify-center items-center mt-8 font-[Roboto]"
                >
                    Показано {{ props.products.from }} по
                    {{ props.products.to }} из {{ props.products.total }}
                </div>
                <div class="flex gap-2 justify-center">
                    <Link
                        v-if="props.products.prev_page_url"
                        :href="props.products.prev_page_url"
                        class="px-4 py-4 border rounded-md border-[black] hover:bg-gray-300"
                    >
                        Назад
                    </Link>
                    <Link
                        v-if="props.products.next_page_url"
                        :href="props.products.next_page_url"
                        class="px-4 py-4 border rounded-md border-[black] hover:bg-gray-300"
                    >
                        Вперед
                    </Link>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
