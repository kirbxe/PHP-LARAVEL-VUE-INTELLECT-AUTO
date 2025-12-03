<script setup>
import AuthenticatedLayout from "@/Layouts/AuthenticatedLayout.vue";
import { Head, Link } from "@inertiajs/vue3";
import Container from "postcss/lib/container";
import { ref } from "vue";

const promotions = ref([
    {
        id: 1,
        title: "Новинка 2025",
        subtitle: "Мега скидка 30% на все фильтры",
        discount: "-30%",
        hasDiscount: true,
        linkText: "Подробнее →",
        width: "770px",
        height: "480px",
        padding: "p-8",
        flexDirection: "flex-row",
        image: "/images/promotions/newcomer.jpg",
        gridArea: "area1",
    },
    {
        id: 2,
        title: "Мега скидки",
        subtitle: "Бесплатная доставка при заказе от 10 000 ₽",
        hasDiscount: false,
        linkText: "Подробнее →",
        width: "340px",
        height: "380px",
        padding: "p-8",
        flexDirection: "flex-col",
        image: "./public/image/coleso.png",
        gridArea: "area2",
    },
    {
        id: 3,
        title: "Мега скидки",
        subtitle: "Сезонное ТО со скидкой",
        hasDiscount: false,
        linkText: "Подробнее →",
        width: "533px",
        height: "185px",
        padding: "p-6",
        flexDirection: "flex-col",
        image: "./images/promotions/service.jpg",
        gridArea: "area3",
    },
    {
        id: 4,
        title: "Мега скидки",
        subtitle: "Второй товар — со скидкой 50%",
        hasDiscount: false,
        linkText: "Подробнее →",
        width: "533px",
        height: "185px",
        padding: "p-6",
        flexDirection: "flex-col",
        image: "/image/coleso.png",
        gridArea: "area4",
    },
]);

const services = ref([
    { label: "Услуги", value: "" },
    { label: "Марка", value: "" },
    { label: "Дата и время", value: "" },
    { label: "Филиал", value: "" },
    { label: "E-mail", value: "" },
    { label: "Имя", value: "" },
]);

const news = ref([
    {
        id: 1,
        title: "Новая поставка оригинальных запчастей",
        description:
            "Мы обновили склад – в наличии новые позиции. Быстрая отгрузка и гарантия качества на все детали.",
        date: "12.11.2024",
    },
    {
        id: 2,
        title: "Теперь доставка в день заказа!",
        description:
            "Для клиентов из Челябинска и области – экспресс-доставка автозапчастей прямо в ваш сервис или на стоянку.",
        date: "10.11.2024",
    },
    {
        id: 3,
        title: "Теперь доставка в день заказа!",
        description:
            "Для клиентов из Челябинска и области – экспресс-доставка автозапчастей прямо в ваш сервис или на стоянку.",
        date: "08.11.2024",
    },
]);

// Методы
const scrollToSection = (sectionId) => {
    const element = document.getElementById(sectionId);
    if (element) {
        element.scrollIntoView({ behavior: "smooth" });
    }
};

const submitForm = () => {
    // Логика отправки формы
    console.log("Форма отправлена");
};
</script>

<template>
    <Head title="Запчасти для коммерческой техники и спецтехники" />

    <AuthenticatedLayout>
        <div class="min-h-screen bg-white">
            <!-- Герой-секция -->
            <div
                class="bg-[url('/image/Glavnai.jpg')] w-full h-screen bg-cover bg-center bg-no-repeat pl-10 pt-32 flex flex-col gap-[60px]"
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
                        Ваш транспорт — это инструмент, который должен работать,
                        а не стоять в ремонте. Мы помогаем механикам, автопаркам
                        и сервисным центрам держать технику в строю, поставляя
                        качественные запчасти для грузовиков, автобусов,
                        спецтехники и прицепов — точно в срок и по лучшей цене.
                    </p>
                </div>
                <button
                    @click="scrollToSection('promotions')"
                    class="bg-[#0075B1] max-w-max rounded-md text-white text-lg font-medium font-[Inter] py-3 px-12 hover:bg-blue-700 transition duration-300"
                >
                    Стать клиентом
                </button>
            </div>

            <!-- Преимущества -->
            <div class="bg-gray-100 w-full px-10 py-5 flex gap-8">
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
                            Работаем с надежными ТК, отправляем в день заказа.
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
                            Наши специалисты помогут найти нужную деталь по VIN,
                            артикулу или фото.
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

            <!-- Секция акций -->
            <section id="promotions" class="py-16 bg-white">
                <div class="container mx-auto px-4">
                    <!-- Заголовок слева -->
                    <div class="text-left mb-12">
                        <h2 class="text-3xl font-bold text-gray-900 mb-4">
                            Акции и скидки
                        </h2>
                        <div class="w-24 h-1 bg-blue-600"></div>
                    </div>

                    <!-- Все карточки в одну строку -->
                    <div
                        class="grid grid-cols-12 grid-rows-2 gap-6 overflow-x-auto pb-4"
                    >
                        <!-- Карточка 1: Большая (667x380) -->
                        <div
                            :class="[
                                promotions[0].bgColor,
                                promotions[0].padding,
                                promotions[0].flexDirection,
                                'row-start-1 row-end-3 col-start-1 col-end-7 rounded-xl bg-[url(/image/coleso.png)] shadow-sm hover:shadow-md transition-shadow border border-blue-100 flex-shrink-0',
                            ]"
                        >
                            <div class="flex flex-col h-full justify-between">
                                <!-- Блок с заголовком -->
                                <div>
                                    <h3 class="text-xl font-bold text-gray-900">
                                        {{ promotions[0].title }}
                                    </h3>
                                    <p class="text-gray-700 mt-2 text-base">
                                        {{ promotions[0].subtitle }}
                                    </p>
                                </div>

                                <!-- Скидка (только для первой карточки) -->
                                <div
                                    v-if="promotions[0].hasDiscount"
                                    class="flex justify-between items-center"
                                >
                                    <span
                                        class="text-4xl font-bold text-red-600"
                                        >{{ promotions[0].discount }}</span
                                    >
                                </div>

                                <!-- Кнопка -->
                                <div class="mt-6">
                                    <button
                                        class="text-blue-600 font-medium hover:text-blue-800 transition flex items-center gap-1 text-base"
                                    >
                                        {{ promotions[0].linkText }}
                                        <svg
                                            class="w-5 h-5"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9 5l7 7-7 7"
                                            ></path>
                                        </svg>
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Карточка 2: Узкая (240x380) -->
                        <div
                            :class="[
                                promotions[1].bgColor,
                                promotions[1].padding,
                                promotions[1].flexDirection,
                                'row-start-1 row-end-3 col-start-7 col-end-9 rounded-xl image shadow-sm hover:shadow-md transition-shadow border  border-blue-100 flex-shrink-0',
                            ]"
                        >
                            <div class="flex flex-col h-full justify-between">
                                <!-- Блок с заголовком -->
                                <div>
                                    <h3 class="text-lg font-bold text-gray-900">
                                        {{ promotions[1].title }}
                                    </h3>
                                    <p class="text-gray-700 mt-2 text-sm">
                                        {{ promotions[1].subtitle }}
                                    </p>
                                </div>

                                <!-- Кнопка -->
                                <div class="text-right mt-4">
                                    <button
                                        class="text-blue-600 font-medium hover:text-blue-800 transition flex items-center justify-end gap-1 text-sm"
                                    >
                                        {{ promotions[1].linkText }}
                                        <svg
                                            class="w-4 h-4"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9 5l7 7-7 7"
                                            ></path>
                                        </svg>
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Карточка 3: Широкая (433x185) -->
                        <div
                            :class="[
                                promotions[2].bgColor,
                                promotions[2].padding,
                                promotions[2].flexDirection,
                                'row-start-1 row-end-2 col-start-9 col-end-13 rounded-xl shadow-sm hover:shadow-md transition-shadow border border-blue-100 flex-shrink-0',
                            ]"
                        >
                            <div class="flex flex-col h-full justify-between">
                                <!-- Блок с заголовком -->
                                <div>
                                    <h3 class="text-lg font-bold text-gray-900">
                                        {{ promotions[2].title }}
                                    </h3>
                                    <p class="text-gray-700 mt-1 text-sm">
                                        {{ promotions[2].subtitle }}
                                    </p>
                                </div>

                                <!-- Кнопка -->
                                <div class="text-right">
                                    <button
                                        class="text-blue-600 font-medium hover:text-blue-800 transition flex items-center justify-end gap-1 text-sm"
                                    >
                                        {{ promotions[2].linkText }}
                                        <svg
                                            class="w-4 h-4"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9 5l7 7-7 7"
                                            ></path>
                                        </svg>
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Карточка 4: Широкая (433x185) -->
                        <div
                            :class="[
                                promotions[3].bgColor,
                                promotions[3].padding,
                                promotions[3].flexDirection,
                                'row-start-2 row-end-3 col-start-9 col-end-13 rounded-xl shadow-sm hover:shadow-md transition-shadow border border-blue-100 flex-shrink-0',
                            ]"
                        >
                            <div class="flex flex-col h-full justify-between">
                                <!-- Блок с заголовком -->
                                <div>
                                    <h3 class="text-lg font-bold text-gray-900">
                                        {{ promotions[3].title }}
                                    </h3>
                                    <p class="text-gray-700 mt-1 text-sm">
                                        {{ promotions[3].subtitle }}
                                    </p>
                                </div>

                                <!-- Кнопка -->
                                <div class="text-right">
                                    <button
                                        class="text-blue-600 font-medium hover:text-blue-800 transition flex items-center justify-end gap-1 text-sm"
                                    >
                                        {{ promotions[3].linkText }}
                                        <svg
                                            class="w-4 h-4"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                        >
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9 5l7 7-7 7"
                                            ></path>
                                        </svg>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Разделитель -->
            <div class="border-t border-gray-200"></div>

            <!-- Секция формы и новостей -->
            <section class="py-16 bg-white">
                <div class="container mx-auto px-4">
                    <!-- Форма заявки -->
                    <div class="max-w-6xl mx-auto mb-16">
                        <h2
                            class="text-3xl font-bold text-show-900 mb-4 text-center"
                        >
                            Работайте с техникой – работайте с профессионалами
                        </h2>
                        <p
                            class="text-gray-600 text-center mb-8 max-w-2xl mx-auto"
                        >
                            Оставьте заявку или позвоните нам – наши специалисты
                            быстро подберут запчасти под ваш транспорт.
                        </p>

                        <div
                            class="bg-white rounded-lg border border-gray-200 overflow-hidden"
                        >
                            <div class="grid grid-cols-7 gap-4 p-6">
                                <!-- Удалены заголовки столбцов, остались только поля ввода -->
                                <div
                                    v-for="(service, index) in services"
                                    :key="index"
                                    class="text-center"
                                >
                                    <input
                                        type="text"
                                        :placeholder="service.label"
                                        class="w-full px-3 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
                                        v-model="service.value"
                                    />
                                </div>
                                <!-- Кнопка Отправить -->
                                <div class="flex items-end">
                                    <button
                                        @click="submitForm"
                                        class="w-full bg-blue-600 text-white py-2 px-4 rounded-md hover:bg-blue-700 transition font-medium"
                                    >
                                        Отправить
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Новости -->
                    <div>
                        <h2
                            class="text-3xl font-bold text-gray-900 mb-8 text-center"
                        >
                            Новости
                        </h2>

                        <div
                            class="flex flex-col md:flex-row gap-6 max-w-7xl mx-auto"
                        >
                            <div
                                v-for="newsItem in news"
                                :key="newsItem.id"
                                class="bg-white rounded-lg border border-gray-200 p-6 hover:shadow-md transition-shadow flex-1 min-w-0"
                            >
                                <div class="flex flex-col h-full">
                                    <div class="mb-4">
                                        <h3
                                            class="text-lg font-bold text-gray-900 mb-2"
                                        >
                                            {{ newsItem.title }}
                                        </h3>
                                        <span class="text-sm text-gray-500">{{
                                            newsItem.date
                                        }}</span>
                                    </div>
                                    <p class="text-gray-600 flex-grow">
                                        {{ newsItem.description }}
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </AuthenticatedLayout>
</template>

<style>
/* Стили для горизонтального скролла карточек */
#promotions .flex-row {
    display: flex;
    flex-wrap: nowrap;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: thin;
    scrollbar-color: #cbd5e1 #f1f5f9;
}

#promotions .flex-row::-webkit-scrollbar {
    height: 8px;
}

#promotions .flex-row::-webkit-scrollbar-track {
    background: #f1f5f9;
    border-radius: 4px;
}

#promotions .flex-row::-webkit-scrollbar-thumb {
    background: #cbd5e1;
    border-radius: 4px;
}

#promotions .flex-row::-webkit-scrollbar-thumb:hover {
    background: #94a3b8;
}

#promotions .flex-shrink-0 {
    flex-shrink: 0;
}

/* Адаптивные стили */
@media (max-width: 1024px) {
    #promotions .flex-row > div {
        min-width: 280px;
        height: 200px !important;
    }

    #promotions .flex-row > div:first-child {
        min-width: 320px;
    }
}

@media (max-width: 768px) {
    #promotions .flex-row > div {
        min-width: 240px;
        height: 180px !important;
    }

    #promotions .flex-row > div:first-child {
        min-width: 280px;
    }
}
</style>
