<template>
    <div class="sort-block">
        <slot></slot>
        
        <!-- Диапазон цены -->
        <PriceRange :filters="filters" />
        
        <!-- Категории -->
        <FilterCheckbox class="text-[18px] font-medium font-inter text-[#313131]"
            title="Категория"
            :options="categories"
            filter-key="categories"
            :filters="filters"
        />
        
        <!-- Бренды -->
        <FilterCheckbox class="text-[18px] font-medium font-inter text-[#313131]"
            title="Бренд"
            :options="brands"
            filter-key="brands"
            :filters="filters"
        />
    </div>
</template>

<script setup>
import PriceRange from './ui/PriceRange.vue';
import FilterCheckbox from './FilterCheckbox.vue';

defineProps({
    categories: {
        type: Array,
        default: () => []
    },
    brands: {
        type: Array,
        default: () => []
    },
    filters: {
        type: Object,
        default: () => ({})
    }
});
</script>