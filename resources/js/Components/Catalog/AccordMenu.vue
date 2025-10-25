<script setup>
import { SearchOutline as SearchIcon } from "@vicons/ionicons5";
import { NIcon, NMenu, NInput, NCheckbox } from "naive-ui";
import { ref } from "vue";
import { h } from "vue";

const searchQuery = ref("");
const PriceIn = ref("");
const PriceOut = ref("");
const expandedKeys = ref(["options"]);

// // Обработчик изменения раскрытых ключей
// const handleExpandedKeys = (keys) => {
//     expandedKeys.value = keys;
// };

const menuOptions = [
    {
        label: "Поиск с полем ввода",
        key: "Search",
        children: [
            {
                key: "search",
                label: () =>
                    h(
                        NInput,
                        {
                            value: searchQuery.value,
                            "onUpdate:value": (value) =>
                                (searchQuery.value = value),
                            placeholder: "",
                            clearable: true,
                            style: { width: "100%" },
                        },
                        {
                            prefix: () =>
                                h(NIcon, null, {
                                    default: () => h(SearchIcon),
                                }),
                        }
                    ),
            },
        ],
    },
    {
        label: "Выбор из списка",
        key: "Select_List_First",
        children: [
            {
                label: "А",
                key: "Select 1",
                children: [
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ATovar1",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ATovar2",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ATovar3",
                    },
                ],
            },
            {
                label: "Б",
                key: "Select 2",
                children: [
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "БTovar1",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "БTovar2",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "БTovar3",
                    },
                ],
            },
            {
                label: "В",
                key: "Select 3",
                children: [
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ВTovar1",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ВTovar2",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ВTovar3",
                    },
                ],
            },
            {
                label: "Г",
                key: "Select 4",
                children: [
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ГTovar1",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ГTovar2",
                    },
                    {
                        label: () =>
                            h(NCheckbox, {
                                label: "АТовар1",
                            }),
                        key: "ГTovar3",
                    },
                ],
            },
        ],
    },
    {
        label: "Выбор из списка",
        key: "Select_List_Second",
        children: [
            {
                label: () =>
                    h(
                        "div",
                        {
                            style: { width: "100%" },
                        },
                        [
                            h(NInput, {
                                value: PriceIn.value,
                                placeholder: "От",
                                clearable: true,
                                style: { width: "100px" },
                            }),
                            h(NInput, {
                                value: PriceIn.value,
                                placeholder: "До",
                                clearable: true,
                                style: { width: "100px" },
                            }),
                        ]
                    ),
                key: "Ninput2",
            },
        ],
    },
];
</script>

<template>
    <n-menu
        :options="menuOptions"
        :default-expanded-keys="defaultExpandedKeys"
        @update:value="handleUpdateValue"
    />
</template>

<style>
.n-menu-item-content--child-active {
    /* --n-item-text-color-active: #ff0000; */
    --n-item-text-color-child-active: #000000;
    --n-item-text-color-child-active-hover: #000000;
    --n-item-text-color-active-hover: #000000;
    --n-arrow-color-active: #ff0000;
    --n-arrow-color-active-hover: #000000;
    --n-arrow-color-child-active: #000000;
    --n-arrow-color-child-active-hover: #000000;
    --n-item-icon-color-active-hover-horizontal: #000000;
    --n-item-icon-color-child-active-horizontal: #000000;
    --n-item-icon-color-child-active-hover-horizontal: #000000;

    --n-item-icon-color-active-hover: #000000;
    --n-item-icon-color-child-active: #000000;
    --n-item-icon-color-child-active-hover: #000000;

    --n-item-icon-color-hover-horizontal: #000000;
    --n-item-icon-color-active-horizontal: #000000;

    --n-item-text-color-hover-horizontal: #000000;
    --n-item-text-color-active-horizontal: #000000;
    --n-item-text-color-child-active-horizontal: #000000;
    --n-item-text-color-child-active-hover-horizontal: #000000;
    --n-item-text-color-active-hover-horizontal: #000000;
}
.n-menu-item-content--selected {
    --n-caret-color: #ff1100;
    --n-border-hover: 1px solid #ff1100;
    --n-border-focus: 1px solid #ff0000;
    --n-loading-color: #ff0000;
}
/* .n-menu-item-content :vertical {
    background-color: #000000;
}
.n-menu-item :focus {
    background-color: #000000;
} */
</style>
