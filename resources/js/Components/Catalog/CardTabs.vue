<template>
    <div class="font-inter max-w-[735px]">
        <div class="flex border-b-2 border-[#E1E1E1]">
            <button 
                v-for="tab in tabs" 
                :key="tab.id" 
                class="px-[70px] py-3 text-lg font-medium cursor-pointer border-b-2 border-transparent"
                :class="{ '!border-[#006598]': activeTab === tab.id }"
                @click="activeTab = tab.id"
            >
                {{ tab.title }}
            </button>
        </div>

        <div class="pt-8">
            <div v-show="activeTab === 'description'" class="tab-pane">
                <slot name="description">
                    <p class="text-[16px] leading-[20px] font-regular text-[#0B0D0D]">
                        Трехкомпонентная присадка для последовательного добавления в бензин. Состав No1 смягчает
                        отложения на форсунках. Состав No2 удаляет размягченные загрязнения. Состав No3 удаляет лаковые
                        и смолистые отложения.
                    </p>
                </slot>
            </div>

            <div v-show="activeTab === 'characteristics'" class="w-[440px]">
                <slot name="characteristics">
                    <div class="flex justify-between">
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
                    <div class="flex justify-between">
                        <CardInfo text="Фасовка" />
                        <CardInfoGrey text="120 мл" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Вес" />
                        <CardInfoGrey text="396 гр" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Длина" />
                        <CardInfoGrey text="170 мм" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Ширина" />
                        <CardInfoGrey text="40 мм" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Высота" />
                        <CardInfoGrey text="220 мм" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Срок годности" />
                        <CardInfoGrey text="60 мес" />
                    </div>
                    <div class="flex justify-between">
                        <CardInfo text="Условия хранения" />
                        <CardInfoGrey text="±30°С" />
                    </div>
                </slot>
            </div>

            <div v-show="activeTab === 'reviews'">
                <slot name="reviews">
                    <div class="review" v-for="review in reviews" :key="review.id">
                        <div class="flex items-start justify-between">
                            <div class="mb-5 flex items-center">
                                <img src="/image/avatar.svg" alt="avatar">
                                <div class="ml-[1rem]">
                                    <p class="mb-[6px] text-[18px] leading-[24px] font-medium text-[#0C0C0C]">{{ review.username }}</p>
                                    <p class="text-[14px] font-regular leading-[20px] text-[#0C0C0C]">{{ review.date }}</p>
                                </div>
                            </div>
                            <div class="flex gap-[10px]">
                                <img src="/image/starblack.svg" alt="starblack">
                                <img src="/image/starblack.svg" alt="starblack">
                                <img src="/image/starblack.svg" alt="starblack">
                                <img src="/image/starblack.svg" alt="starblack">
                                <img src="/image/starempty.svg" alt="starempty">
                            </div>
                        </div>
                        <p class="mb-5 text-[1rem] font-regular leading-[20px] text-[#0C0C0C]">{{ review.text }}</p>
                        <div v-if="review.images && review.images.length" class="flex gap-[10px]">
                            <img 
                                v-for="(image, index) in review.images.slice(0, 2)" 
                                :key="index"
                                :src="image"
                            >
                        </div>
                    </div>
                </slot>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import CardInfo from "@/Components/Catalog/CardInfo.vue";
import CardInfoGrey from "@/Components/Catalog/CardInfoGrey.vue";

const activeTab = ref('description')

const tabs = [
    { id: 'description', title: 'Описание' },
    { id: 'characteristics', title: 'Характеристики' },
    { id: 'reviews', title: 'Отзывы (2)' }
]

const props = defineProps({
    reviews: {
        type: Array,
        default: () => [
            {
                id: 1,
                username: 'Имя пользователя',
                date: '30.01.2025',
                text: 'Быстрая доставка и вежливый менеджер. Заказал предохранители и фильтры — всё пришло вовремя, аккуратно упаковано. Буду обращаться ещё.'
            },
            {
                id: 2,
                username: 'Имя пользователя',
                date: '30.01.2025',
                text: 'Нужная деталь была в наличии, оформили заказ за пару минут. Цены адекватные, качество отличное. Особенно удобно, что можно сразу подобрать аналоги по VIN — экономит кучу времени.',
                images: [
                    '/image/square.svg',
                    '/image/square.svg'
                ]
            }
        ]
    }
})
</script>