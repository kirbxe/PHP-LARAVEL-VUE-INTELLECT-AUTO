<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import { computed } from "vue";
import Catalog from "@/Components/Catalog/Catalog.vue";
import SortBlock from "@/Components/Catalog/SortBlock.vue";
import TitleItem from "@/Components/Catalog/ui/TitleItem.vue";
import CardProduct from "@/Components/Catalog/CardProduct.vue";
import Breadcrumbs from "@/Components/Catalog/ui/Breadcrumbs.vue";
import SortBreadcrumbs from "@/Components/Catalog/SortBreadcrumbs.vue";

const props = defineProps({ products: Object });

const pageKey = computed(() => props.products.current_page);

const visiblePages = computed(() => {
    const current = props.products.current_page;
    const last = props.products.last_page;
    const pages = [];

    let start = current - 1;
    let end = current + 1;

    if (current === 1) {
        start = 1;
        end = Math.min(last, 3);
    } else if (current === last) {
        start = Math.max(1, last - 2);
        end = last;
    }

    for (let i = start; i <= end; i++) {
        if (i >= 1 && i <= last) {
            pages.push(i);
        }
    }

    return pages;
});

const generatePageUrl = (page) => {
    return props.products.path + "?page=" + page;
};
</script>

<template>
    <AuthenticatedLayout>
        <Head title="Product" />
        <div :key="pageKey">
            <div
                class="max-w-[1360px] mx-auto flex justify-center bg-[#F7F7F7]"
            >
                <div class="pt-4 w-full">
                    <div class="flex justify-between gap-8">
                        <div>
                            <SortBlock>
                                <SortBreadcrumbs>
                                    <Link
                                        class="font-inter pr-1 text-[12px] text-[#707070] min-w-max h-auto"
                                        href="/dashboard"
                                        >Главная</Link
                                    >
                                    <Breadcrumbs text="/ Каталог товаров" />
                                </SortBreadcrumbs>
                                <TitleItem Title="Каталог товаров" />
                            </SortBlock>
                        </div>

                        <div>
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

                            <div class="flex flex-col justify-center mt-[25px] mb-[60px]">
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
                                            <path
                                                fill="#707070"
                                                d="M12.707 17.293L8.414 13H18v-2H8.414l4.293-4.293l-1.414-1.414L4.586 12l6.707 6.707z"
                                            />
                                        </svg>
                                    </Link>

                                    <Link
                                        v-for="page in visiblePages"
                                        :key="page"
                                        :href="generatePageUrl(page)"
                                        :class="[
                                            'w-[44px] h-[44px] flex items-center justify-center border rounded-md border-[#F1F1F1] hover:bg-gray-300',
                                            page === props.products.current_page
                                                ? 'bg-blue-500 border-blue-500 text-white'
                                                : 'bg-white text-[#707070]',
                                        ]"
                                    >
                                        {{ page }}
                                    </Link>

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
                                            <path
                                                fill="#707070"
                                                d="m11.293 17.293l1.414 1.414L19.414 12l-6.707-6.707l-1.414 1.414L15.586 11H6v2h9.586z"
                                            />
                                        </svg>
                                    </Link>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>