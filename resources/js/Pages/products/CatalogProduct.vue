<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import { computed } from "vue";
import Catalog from "@/Components/Catalog/Catalog.vue";
import SortBlock from "@/Components/Catalog/SortBlock.vue";
import TitleItem from "@/Components/Catalog/ui/TitleItem.vue";
import AccordMenu from "@/Components/Catalog/AccordMenu.vue";
import CardProduct from "@/Components/Catalog/CardProduct.vue";

const props = defineProps({ products: Object });

const pageKey = computed(() => props.products.current_page);
</script>

<template>
    <AuthenticatedLayout>
        <Head title="Product" />
        <div :key="pageKey">
            <div class="flex justify-center bg-[#F7F7F7]">
                <div class="px-10 py-4 flex">
                    <
                    <SortBlock>
                        <TitleItem Title="Каталог товаров" />
                    </SortBlock>

                    <Catalog>
                        <div
                            v-for="product in props.products.data"
                            :key="product.id"
                        >
                            <CardProduct
                                :Name="product.name"
                                :Price="product.price"
                                :OldPrice="product.price"
                                :Image="product.picture1"
                                :PackagingText="product.packaging"
                                TextButton="Купить"
                            />
                        </div>
                    </Catalog>
                </div>
            </div>

            <div class="flex flex-col justify-center">
                <div class="flex gap-2 justify-center">
                    <Link
                        v-if="props.products.prev_page_url"
                        :href="props.products.prev_page_url"
                        class="p-3 border rounded-md bg-white border-[#F1F1F1] hover:bg-gray-300"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="20"
                            height="20"
                            viewBox="0 0 24 24"
                        >
                            <title>Left-arrow-alt SVG Icon</title>
                            <path
                                fill="#707070"
                                d="M12.707 17.293L8.414 13H18v-2H8.414l4.293-4.293l-1.414-1.414L4.586 12l6.707 6.707z"
                            />
                        </svg>
                    </Link>
                    <div
                        class="w-[44px] h-[44px] flex items-center justify-center border rounded-md bg-white border-[#F1F1F1] hover:bg-gray-300 text-[#707070]"
                    >
                        {{ props.products.current_page }}
                    </div>
                    <Link
                        v-if="props.products.next_page_url"
                        :href="props.products.next_page_url"
                        class="p-3 border rounded-md bg-white border-[#F1F1F1] hover:bg-gray-300"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="20"
                            height="20"
                            viewBox="0 0 24 24"
                        >
                            <title>Right-arrow-alt SVG Icon</title>
                            <path
                                fill="#707070"
                                d="m11.293 17.293l1.414 1.414L19.414 12l-6.707-6.707l-1.414 1.414L15.586 11H6v2h9.586z"
                            />
                        </svg>
                    </Link>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
