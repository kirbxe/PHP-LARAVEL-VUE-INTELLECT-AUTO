<template>
    <div class="price-slider">
            <div class="slider-track"></div>
            <input
                type="range"
                min="0"
                max="50000"
                step="100"
                v-model="minPrice"
                class="slider slider-min"
                @input="handleSliderChange" 
            >
            <input
                type="range"
                min="0"
                max="50000"
                step="100"
                v-model="maxPrice"
                class="slider slider-max"
                @input="handleSliderChange"
            >
        </div>
    <div class="price-range">
        <div class="price-inputs">
            <div class="price-input-group">
                <label class="price-label">от</label>
                <input
                    v-model="minPrice"
                    type="number"
                    class="price-input"
                    placeholder="0"
                    @input="handlePriceChange"
                >
            </div>
            <div class="price-input-group">
                <label class="price-label">до</label>
                <input
                    v-model="maxPrice"
                    type="number"
                    class="price-input"
                    placeholder="50000"
                    @input="handlePriceChange"
                >
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const props = defineProps({
    filters: Object
});

const minPrice = ref(props.filters.min_price || 0);
const maxPrice = ref(props.filters.max_price || 50000);

const handlePriceChange = () => {
    debouncedFilter();
};

const handleSliderChange = () => {
    debouncedFilter();
};
// Следим за изменениями фильтров из props
watch(() => props.filters, (newFilters) => {
    minPrice.value = newFilters.min_price || 0;
    maxPrice.value = newFilters.max_price || 50000;
});
</script>

<style scoped>
.price-range {
    padding: 16px 0 32px 0;
    max-width: 198px;
}

.price-inputs {
    display: flex;
}

.price-input-group {
    flex: 1;
    position: relative;
}

.price-label {
    position: absolute;
    left: 12px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 14px;
    color: #707070;
}

.price-input {
    width: 93.25px;
    height: 36px;
    padding: 8px 12px 8px 30px;
    border: 1px solid #F1F1F1;
    border-radius: 10px;
}

.price-input:focus {
    outline: none;
    border-color: #007bff;
}

.price-slider {
    position: relative;
    height: 4px;
    background: #E5E5E5;
    border-radius: 2px;
    margin: 20px 0;
    max-width: 198px;
}

.slider-track {
    position: absolute;
    height: 100%;
    background: #007BFF;
    border-radius: 2px;
    left: 0%;
    right: 0%;
}

.slider {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 100%;
    height: 4px;
    background: transparent;
    pointer-events: none;
    -webkit-appearance: none;
    appearance: none;
}

.slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 20px;
    height: 20px;
    background: #FFFFFF;
    border: 1px solid #E5E5E5;
    border-radius: 4px;
    cursor: pointer;
    pointer-events: all;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: all 0.2s ease;
}

.slider::-webkit-slider-thumb:hover {
    border-color: #007BFF;
    box-shadow: 0 2px 8px rgba(0, 123, 255, 0.3);
}

.slider::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background: #FFFFFF;
    border: 1px solid #E5E5E5;
    border-radius: 4px;
    cursor: pointer;
    pointer-events: all;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    transition: all 0.2s ease;
}
.slider::-moz-range-thumb:hover {
    border-color: #007BFF;
    box-shadow: 0 2px 8px rgba(0, 123, 255, 0.3);
}
</style>