<script setup>
import { ref } from "vue";
import Dropdown from "@/Components/Dropdown.vue";
import DropdownLink from "@/Components/DropdownLink.vue";
import NavLink from "@/Components/NavLink.vue";
import ResponsiveNavLink from "@/Components/ResponsiveNavLink.vue";

const showingNavigationDropdown = ref(false);

const selectedCity = ref("clb");

const cities = [
    { value: "clb", label: "Челябинск" },
    { value: "ekb", label: "Екатеринбург" },
];

const buyers = [
    { value: "buyerNav_1", href_buyer: "#", aText: "Акции" },
    { value: "buyerNav_2", href_buyer: "#", aText: "О компании" },
    { value: "buyerNav_3", href_buyer: "#", aText: "Доставка" },
    { value: "buyerNav_4", href_buyer: "#", aText: "Адреса" },
    { value: "buyerNav_5", href_buyer: "#", aText: "Контакты" },
];
const informations = [
    { value: "informationNav_1", href_information: "#", aText: "Реквизиты" },
    { value: "informationNav_2", href_information: "#", aText: "Офферта" },
    {
        value: "informationNav_3",
        href_information: "#",
        aText: "Политика конфиденциальности",
    },
];
const contacts = [
    { value: "contactNav_2", href_contact: "#", aText: "8 (900) 000 00 00" },
    { value: "contactNav_1", href_contact: "#", aText: "email@gmail.com" },
    {
        value: "contactNav_3",
        href_contact: "#",
        aText: "г. Челябинск, ул. Разина, д. 3 офис 908/19",
    },
];
</script>

<template>
    <div>
        <div class="min-h-screen bg-[#F7F7F7] flex flex-col">
            <nav class="border-b border-gray-100 py-3 bg-white">
                <!-- Primary Navigation Menu -->
                <!-- Хэдер его состовляющие и Навигационные элементы, при ширине 1440пкс -->
                <div class="max-w-[1360px] flex flex-col mx-auto gap-2">
                    <div
                        class="flex w-full text-[#929292] text-xs font-normal font-Inter leading-4 font-[Inter]"
                    >
                        <div class="flex flex-1 flex-row gap-2">
                            <p class="text-gray-400">Ваш город:</p>
                            <select
                                v-model="selectedCity"
                                class="text-gray-500 max-w-max py-0 pr-auto border-0 text-xs focus:outline-none focus:ring-0"
                            >
                                <option
                                    v-for="city in cities"
                                    :key="city.value"
                                    :value="city.value"
                                    class="text-gray-700"
                                >
                                    {{ city.label }}
                                </option>
                            </select>
                        </div>
                        <div
                            class="flex flex-1 space-x-10 sm:-my-px sm:ms-10 sm:flex"
                        >
                            <NavLink
                                :href="route('dashboard')"
                                :active="route().current('dashboard')"
                            >
                                Акции
                            </NavLink>
                            <NavLink
                                :href="route('dashboard')"
                                :active="route().current('dashboard')"
                            >
                                О компании
                            </NavLink>
                            <NavLink
                                :href="route('dashboard')"
                                :active="route().current('dashboard')"
                            >
                                Адреса
                            </NavLink>
                            <NavLink
                                :href="route('dashboard')"
                                :active="route().current('dashboard')"
                            >
                                Контакты
                            </NavLink>
                        </div>
                        <div class="flex flex-1 justify-end">
                            <p class="">8 (900) 000 00 00</p>
                        </div>
                    </div>
                    <div class="w-full h-[0.5px] bg-gray-300"></div>
                    <div class="flex gap-20">
                        <div class="flex">
                            <a :href="route('dashboard')">
                                <img
                                    src="../../../public/image/IntelectAuto.svg"
                                    alt="IntelectAuto"
                                />
                            </a>
                        </div>
                        <div class="flex gap-2 w-[880px]">
                            <a
                                :href="route('products.index')"
                                class="flex items-center gap-2.5 text-white bg-[#0075B1] px-2.5 py-2 rounded-md"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    width="20"
                                    height="20"
                                    viewBox="0 0 24 24"
                                >
                                    <title>Hamburger SVG Icon</title>
                                    <path
                                        fill="#ffffff"
                                        d="M21 18H3v-2h18v2Zm0-5H3v-2h18v2Zm0-5H3V6h18v2Z"
                                    />
                                </svg>
                                Каталог
                            </a>
                            <input
                                type="text"
                                style="
                                    background-position-x: 14px;
                                    background-position-y: 11px;
                                    background-size: 15px;
                                "
                                class="block p-2 pl-10 bg- mx-auto bg-[url('/image/Search.svg')] bg-no-repeat border-1 border-gray-200 rounded-lg placeholder-gray-500 w-full"
                                placeholder="Поиск"
                            />
                        </div>
                        <div class="mx-auto max-w-full px-4 sm:px-6 lg:px-8">
                            <div class="flex h-auto flex-col mx-auto">
                                <!-- Логин/Регистрация -->
                                <div
                                    class="hidden sm:ms-6 sm:flex sm:items-center"
                                >
                                    <!-- Settings Dropdown -->
                                    <div class="relative ms-3">
                                        <Dropdown align="right" width="48">
                                            <template #trigger>
                                                <span
                                                    class="inline-flex rounded-md"
                                                >
                                                    <button
                                                        type="button"
                                                        class="inline-flex items-center rounded-md border border-transparent bg-white px-3 py-2 text-sm font-medium leading-4 text-gray-500 transition duration-150 ease-in-out hover:text-gray-700 focus:outline-none"
                                                    >
                                                        {{
                                                            $page.props.auth
                                                                .user.name
                                                        }}

                                                        <svg
                                                            class="-me-0.5 ms-2 h-4 w-4"
                                                            xmlns="http://www.w3.org/2000/svg"
                                                            viewBox="0 0 20 20"
                                                            fill="currentColor"
                                                        >
                                                            <path
                                                                fill-rule="evenodd"
                                                                d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                                                clip-rule="evenodd"
                                                            />
                                                        </svg>
                                                    </button>
                                                </span>
                                            </template>

                                            <template #content>
                                                <DropdownLink
                                                    :href="
                                                        route('profile.edit')
                                                    "
                                                >
                                                    Profile
                                                </DropdownLink>
                                                <DropdownLink
                                                    :href="route('logout')"
                                                    method="post"
                                                    as="button"
                                                >
                                                    Log Out
                                                </DropdownLink>
                                            </template>
                                        </Dropdown>
                                    </div>
                                </div>

                                <!-- Hamburger При адаптиве-->
                                <div class="-me-2 flex items-center sm:hidden">
                                    <button
                                        @click="
                                            showingNavigationDropdown =
                                                !showingNavigationDropdown
                                        "
                                        class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 transition duration-150 ease-in-out hover:bg-gray-100 hover:text-gray-500 focus:bg-gray-100 focus:text-gray-500 focus:outline-none"
                                    >
                                        <svg
                                            class="h-6 w-6"
                                            stroke="currentColor"
                                            fill="none"
                                            viewBox="0 0 24 24"
                                        >
                                            <path
                                                :class="{
                                                    hidden: showingNavigationDropdown,
                                                    'inline-flex':
                                                        !showingNavigationDropdown,
                                                }"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M4 6h16M4 12h16M4 18h16"
                                            />
                                            <path
                                                :class="{
                                                    hidden: !showingNavigationDropdown,
                                                    'inline-flex':
                                                        showingNavigationDropdown,
                                                }"
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M6 18L18 6M6 6l12 12"
                                            />
                                        </svg>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Responsive Navigation Menu (Положение при адаптиве)-->
                <div
                    :class="{
                        block: showingNavigationDropdown,
                        hidden: !showingNavigationDropdown,
                    }"
                    class="sm:hidden"
                >
                    <div class="space-y-1 pb-3 pt-2">
                        <ResponsiveNavLink
                            :href="route('dashboard')"
                            :active="route().current('dashboard')"
                        >
                            Dashboard
                        </ResponsiveNavLink>
                    </div>

                    <!-- Responsive Settings Options -->
                    <div class="border-t border-gray-200 pb-1 pt-4">
                        <div class="px-4">
                            <div class="text-base font-medium text-gray-800">
                                {{ $page.props.auth.user.name }}
                            </div>
                            <div class="text-sm font-medium text-gray-500">
                                {{ $page.props.auth.user.email }}
                            </div>
                        </div>

                        <div class="mt-3 space-y-1">
                            <ResponsiveNavLink :href="route('profile.edit')">
                                Profile
                            </ResponsiveNavLink>
                            <ResponsiveNavLink
                                :href="route('logout')"
                                method="post"
                                as="button"
                            >
                                Log Out
                            </ResponsiveNavLink>
                        </div>
                    </div>
                </div>
            </nav>

            <!-- Page Heading -->
            <header class="bg-white shadow" v-if="$slots.header">
                <div class="mx-auto max-w-7xl px-4 py-6 sm:px-6 lg:px-8">
                    <slot name="header" />
                </div>
            </header>

            <!-- Page Content -->
            <main class="flex-1">
                <slot />
            </main>
            <footer
                class="bg-white border-t border-gray-200 mt-auto font-[Inter]"
            >
                <div class="border-b border-gray-100 py-3 bg-white">
                    <div
                        class="max-w-[1360px] flex mx-auto gap-2 pt-10 pb-[86px]"
                    >
                        <div class="flex flex-1 flex-col gap-16">
                            <div class="flex flex-col gap-6">
                                <a :href="route('dashboard')">
                                    <img
                                        src="../../../public/image/IntelectAuto.svg"
                                        alt="IntelectAuto"
                                        width="160"
                                    />
                                </a>
                                <div class="flex gap-2.5">
                                    <a href=""
                                        ><img
                                            src="../../../public/image/VKicon.svg"
                                            alt=""
                                    /></a>
                                    <a href="">
                                        <img
                                            src="../../../public/image/Telegramicon.svg"
                                            alt=""
                                    /></a>
                                    <a href="">
                                        <img
                                            src="../../../public/image/Mailicon.svg"
                                            alt=""
                                    /></a>
                                </div>
                            </div>
                            <p
                                class="text-[12px] font-regular font-inter text-gray-500"
                            >
                                &copy; ООО Интеллект-Авто 2025
                            </p>
                        </div>
                        <div class="flex gap-5">
                            <ul class="flex flex-col gap-3">
                                <li class="flex mb-2 text-[#313131]">
                                    Покупателям
                                </li>
                                <li
                                    v-for="buyer in buyers"
                                    :key="buyer.value"
                                    :value="buyer.value"
                                    class="text-gray-500 text-xs font-normal w-[150px] leading-4"
                                >
                                    <a :href="buyer.href_buyer">{{
                                        buyer.aText
                                    }}</a>
                                </li>
                            </ul>
                            <ul class="flex flex-col gap-3">
                                <li class="flex mb-2 text-[#313131]">
                                    Информация
                                </li>
                                <li
                                    v-for="info in informations"
                                    :key="info.value"
                                    :value="info.value"
                                    class="text-gray-500 text-xs font-normal w-[150px] leading-4"
                                >
                                    <a :href="info.href_information">{{
                                        info.aText
                                    }}</a>
                                </li>
                            </ul>
                            <ul class="flex flex-col gap-3">
                                <li class="flex mb-2 text-[#313131]">
                                    Контакты
                                </li>
                                <li
                                    v-for="contact in contacts"
                                    :key="contact.value"
                                    :value="contact.value"
                                    class="text-gray-500 text-xs font-normal w-[150px] leading-4"
                                >
                                    {{ contact.aText }}
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </footer>
        </div>
    </div>
</template>
