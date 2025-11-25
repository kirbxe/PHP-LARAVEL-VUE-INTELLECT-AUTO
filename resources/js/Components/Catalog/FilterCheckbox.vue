<template>
    <div class="filter-section">
        <h3 class="filter-title">{{ title }}</h3>
        <div class="filter-options">
            <label
                v-for="option in options"
                :key="option.id"
                class="filter-option"
            >
                <input
                    type="checkbox"
                    :value="option.id"
                    :checked="isChecked(option.id)"
                    @change="handleChange(option.id, $event.target.checked)"
                    class="filter-checkbox"
                >
                <span class="checkmark"></span>
                <span class="option-text">{{ option.name }}</span>
            </label>
        </div>
    </div>
</template>

<script setup>
import { router } from '@inertiajs/vue3';

const props = defineProps({
    title: String,
    options: Array,
    filterKey: String,
    filters: Object
});

const isChecked = (id) => {
    const currentValues = props.filters[props.filterKey] || [];
    return currentValues.includes(id.toString());
};

const handleChange = (id, checked) => {
    const currentValues = props.filters[props.filterKey] || [];
    let newValues;

    if (checked) {
        newValues = [...currentValues, id.toString()];
    } else {
        newValues = currentValues.filter(value => value !== id.toString());
    }

    router.get(route('products.index'), {
        ...props.filters,
        [props.filterKey]: newValues
    }, {
        preserveState: true,
        replace: true
    });
};
</script>