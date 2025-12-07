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
import CardInfoGrey from "@/Components/Catalog/CardInfoGrey.vue";
import CardButton from "@/Components/Catalog/CardButton.vue";
import CardTabs from "@/Components/Catalog/CardTabs.vue";
import CardReview from "@/Components/Catalog/CardReview.vue";
import TitleItem from "@/Components/Catalog/ui/TitleItem.vue";
</script>
<template>
    <Head title="Card" />
    <AuthenticatedLayout>
        <div
            class="max-w-[1360px] mx-auto bg-[#F7F7F7] pt-4"
        >
            <div class="mb-[64px]">
                <SortBreadcrumbs class="mb-2">
                    <Link
                        class="pr-1 font-inter text-[12px] text-[#707070] min-w-max h-auto"
                        href="/dashboard"
                        >Главная</Link
                    >
                    <Link
                        class="pr-1 font-inter text-[12px] text-[#707070] min-w-max h-auto"
                        href="/products"
                        >/ Каталог товаров</Link
                    >
                    <Breadcrumbs text="/ Карточка товара" />
                </SortBreadcrumbs>

                <div class="flex">
                    <Carousel />
                    <div class="ml-10 max-w-[635px]">
                        <CardTitle
                            text="LAVR Трехуровневая очистка топливной системы ML100 Petrol, 120 мл, кор (20 шт)"
                        />
                        <CardAvailability text="В наличии" />
                        <div class="flex">
                            <CardTitle text="908 ₽" />
                            <CardOldPrice text="2 000 ₽" />
                        </div>

                        <div class="flex justify-between mt-[32px]">
                            <CardInfo text="Артикул" />
                            <CardInfoGrey text="Ln2137" />
                        </div>
                        <div class="flex justify-between">
                            <CardInfo text="Бренд" />
                            <CardInfoGrey text="LAVR" />
                        </div>
                        <div class="flex justify-between">
                            <CardInfo text="Категория" />
                            <CardInfoGrey text="Присадки в топливо" />
                        </div>
                        <CardButton text="Купить сейчас" />
                    </div>
                </div>
            </div>

            <div class="h-[484px] flex justify-between">
                <CardTabs />
                <CardReview />
            </div>

            <div class="h-[454px] mt-[50px] flex justify-between items-start">
                <TitleItem Title="С этим товаром часто покупают"/>
                <div class="flex gap-[21px] ">
                    <img src="/image/leftarrow.svg" alt="">
                    <img class="mr-[11px]" src="/image/rightarrow.svg" alt="">
                </div>
            </div>
            
        </div>
    </AuthenticatedLayout>

</template>