<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import Breadcrumbs from "@/Components/Catalog/ui/Breadcrumbs.vue";
import SortBreadcrumbs from "@/Components/Catalog/SortBreadcrumbs.vue";
import Carousel from "@/Components/Catalog/Carousel.vue";
</script>

<template>

    <Head title="CardInfo" />
    <AuthenticatedLayout>

        <div class="max-w-[1360px] mx-auto flex justify-between bg-[#F7F7F7] pt-4">

            <div>
                <SortBreadcrumbs class="mb-2">
                    <Link class="pr-1 font-inter text-[12px] text-[#707070] min-w-max h-auto" href="/dashboard">Главная</Link>
                    <Link class="pr-1 font-inter text-[12px] text-[#707070] min-w-max h-auto" href="/products">/ Каталог товаров</Link>
                    <Breadcrumbs text="/ Карточка товара" />
                </SortBreadcrumbs>

                <div class="">
                        <Carousel />
                    <div class=""></div>
                    <div class=""></div>
                </div>
            </div>

        </div>

    </AuthenticatedLayout>

</template>