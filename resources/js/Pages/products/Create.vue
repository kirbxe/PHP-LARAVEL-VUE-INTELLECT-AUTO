<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import Breadcrumbs from "@/Components/Catalog/ui/Breadcrumbs.vue";
import SortBreadcrumbs from "@/Components/Catalog/SortBreadcrumbs.vue";
import Carousel from "@/Components/Catalog/Carousel.vue";
import CardTitle from "@/Components/Catalog/CardTitle.vue";
import CardAvailability from "@/Components/Catalog/CardAvailability.vue";
import CardOldPrice from "@/Components/Catalog/CardOldPrice.vue";
import CardInfo from "@/Components/Catalog/CardInfo.vue";
import CardArticle from "@/Components/Catalog/CardArticle.vue";
import CardBrend from "@/Components/Catalog/CardBrend.vue";
import CardCategory from "@/Components/Catalog/CardCategory.vue";
import CardButton from "@/Components/Catalog/CardButton.vue";
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

                <div class="flex">
                    <Carousel />
                    <div class="ml-10 max-w-[610px]">
                        
                        <CardTitle text="LAVR Трехуровневая очистка топливной системы ML100 Petrol, 120 мл, кор (20 шт)" />
                        <CardAvailability text="В наличии"/>
                        <div class="flex">
                            <CardTitle text="908 ₽" />
                            <CardOldPrice text="2 000 ₽" />
                        </div>
                        
                        <div class="flex justify-between mt-[32px]">
                            <CardInfo text="Артикул"/> <CardArticle text="Ln2137"/> 
                        </div>
                        <div class="flex justify-between">
                            <CardInfo text="Бренд"/> <CardBrend text="LAVR"/> 
                        </div>
                        <div class="flex justify-between">
                            <CardInfo text="Категория"/> <CardCategory text="Присадки в топливо"/> 
                        </div>
                        <CardButton text="Купить сейчас" />
                    </div>
                </div>

            </div>

        </div>
    </AuthenticatedLayout>

</template>