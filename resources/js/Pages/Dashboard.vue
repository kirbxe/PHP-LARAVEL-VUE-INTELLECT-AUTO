<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head } from "@inertiajs/vue3";
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <div class="">
            <div class="">
                <div
                    class="bg-[url('/image/BackgroundGeneratPage.svg')] w-full h-screen bg-cover bg-center bg-no-repeat pl-10 pt-32 flex flex-col gap-[60px]"
                >
                    <div class="flex flex-col gap-4 h-auto">
                        <h1
                            class="text-white text-7xl font-bold font-[IBMPlexSans] leading-[72px]"
                        >
                            Запчасти <br />
                            для коммерческой <br />
                            техники и спецтехники
                        </h1>
                        <p
                            class="text-gray-100 text-sm font-normal font-[Inter] w-[618px]"
                        >
                            Ваш транспорт — это инструмент, который должен
                            работать, а не стоять в ремонте. Мы помогаем
                            механикам, автопаркам и сервисным центрам держать
                            технику в строю, поставляя качественные запчасти для
                            грузовиков, автобусов, спецтехники и прицепов —
                            точно в срок и по лучшей цене.
                        </p>
                    </div>
                    <a
                        href=""
                        class="bg-[#0075B1] max-w-max rounded-md text-white text-lg font-medium font-[Inter] py-3 px-12"
                        >Стать клиентом</a
                    >
                </div>
                <div class="bg-gray-300 w-full px-10 py-5 flex gap-8">
                    <div class="flex flex-1 gap-2">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="30"
                            height="30"
                            viewBox="0 0 16 16"
                            class="p-[0.5]"
                        >
                            <title>Heart SVG Icon</title>
                            <path
                                fill="#0075b1"
                                d="m8 2.748l-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385c.92 1.815 2.834 3.989 6.286 6.357c3.452-2.368 5.365-4.542 6.286-6.357c.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15"
                            />
                        </svg>
                        <div
                            class="flex flex-col gap-1 font-[IBMPlexSans] w-[180px] leading-auto"
                        >
                            <h3 class="text-gray-600 font-normal text-sm">
                                Широкий ассортимент
                            </h3>
                            <p class="text-gray-500 font-normal text-xs">
                                Запчасти для европейских, российских и китайских
                                марок: от двигателя до подвески.
                            </p>
                        </div>
                    </div>
                    <div class="bg-gray-600 w-[1px] flex"></div>
                    <div class="flex flex-1 gap-2">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="30"
                            height="30"
                            viewBox="0 0 16 16"
                            class="p-[0.5]"
                        >
                            <title>Heart SVG Icon</title>
                            <path
                                fill="#0075b1"
                                d="m8 2.748l-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385c.92 1.815 2.834 3.989 6.286 6.357c3.452-2.368 5.365-4.542 6.286-6.357c.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15"
                            />
                        </svg>
                        <div
                            class="flex flex-col gap-1 font-[IBMPlexSans] w-[180px] leading-auto"
                        >
                            <h3 class="text-gray-600 font-normal text-sm">
                                Проверенные поставщики
                            </h3>
                            <p class="text-gray-500 font-normal text-xs">
                                Оригинал и надежные аналоги от ведущих брендов.
                            </p>
                        </div>
                    </div>
                    <div class="bg-gray-600 w-[1px] flex"></div>
                    <div class="flex flex-1 gap-2">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="30"
                            height="30"
                            viewBox="0 0 16 16"
                            class="p-[0.5]"
                        >
                            <title>Heart SVG Icon</title>
                            <path
                                fill="#0075b1"
                                d="m8 2.748l-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385c.92 1.815 2.834 3.989 6.286 6.357c3.452-2.368 5.365-4.542 6.286-6.357c.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15"
                            />
                        </svg>
                        <div
                            class="flex flex-col gap-1 font-[IBMPlexSans] w-[180px] leading-auto"
                        >
                            <h3 class="text-gray-600 font-normal text-sm">
                                Быстрая доставка по РФ
                            </h3>
                            <p class="text-gray-500 font-normal text-xs">
                                Работаем с надежными ТК, отправляем в день
                                заказа.
                            </p>
                        </div>
                    </div>
                    <div class="bg-gray-600 w-[1px] flex"></div>
                    <div class="flex flex-1 gap-2">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="30"
                            height="30"
                            viewBox="0 0 16 16"
                            class="p-[0.5]"
                        >
                            <title>Heart SVG Icon</title>
                            <path
                                fill="#0075b1"
                                d="m8 2.748l-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385c.92 1.815 2.834 3.989 6.286 6.357c3.452-2.368 5.365-4.542 6.286-6.357c.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15"
                            />
                        </svg>
                        <div
                            class="flex flex-col gap-1 font-[IBMPlexSans] w-[180px] leading-auto"
                        >
                            <h3 class="text-gray-600 font-normal text-sm">
                                Помощь в подборе
                            </h3>
                            <p class="text-gray-500 font-normal text-xs">
                                Наши специалисты помогут найти нужную деталь по
                                VIN, артикулу или фото.
                            </p>
                        </div>
                    </div>
                    <div class="bg-gray-600 w-[1px] flex"></div>
                    <div class="flex flex-1 gap-2">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="30"
                            height="30"
                            viewBox="0 0 16 16"
                            class="p-[0.5]"
                        >
                            <title>Heart SVG Icon</title>
                            <path
                                fill="#0075b1"
                                d="m8 2.748l-.717-.737C5.6.281 2.514.878 1.4 3.053c-.523 1.023-.641 2.5.314 4.385c.92 1.815 2.834 3.989 6.286 6.357c3.452-2.368 5.365-4.542 6.286-6.357c.955-1.886.838-3.362.314-4.385C13.486.878 10.4.28 8.717 2.01zM8 15C-7.333 4.868 3.279-3.04 7.824 1.143q.09.083.176.171a3 3 0 0 1 .176-.17C12.72-3.042 23.333 4.867 8 15"
                            />
                        </svg>
                        <div
                            class="flex flex-col gap-1 font-[IBMPlexSans] w-[180px] leading-auto"
                        >
                            <h3 class="text-gray-600 font-normal text-sm">
                                Оплата, как удобно
                            </h3>
                            <p class="text-gray-500 font-normal text-xs">
                                Для юрлиц и ИП, безналичный расчет, отсрочка
                                постоянным клиентам.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
