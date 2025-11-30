<template>
    <div class="price-slider">
        <div class="slider-track" ref="sliderTrack"></div>
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
                <input
                    v-model="minPrice"
                    type="number"
                    class="price-input"
                    placeholder="0"
                    @input="handlePriceChange"
                >
                <img src="/image/rub.svg" alt="руб" class="currency-icon">
            </div>
            <div class="price-input-group">
                <input
                    v-model="maxPrice"
                    type="number"
                    class="price-input"
                    placeholder="50000"
                    @input="handlePriceChange"
                >
                <img src="/image/rub.svg" alt="руб" class="currency-icon">
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue';

const props = defineProps({
    filters: Object
});

const minPrice = ref(props.filters.min_price || 0);
const maxPrice = ref(props.filters.max_price || 50000);
const sliderTrack = ref(null);

const handlePriceChange = () => {
    updateSliderTrack();
    debouncedFilter();
};

const handleSliderChange = () => {
    updateSliderTrack();
    debouncedFilter();
};

watch(() => props.filters, (newFilters) => {
    minPrice.value = newFilters.min_price || 0;
    maxPrice.value = newFilters.max_price || 50000;
    updateSliderTrack();
});

onMounted(() => {
    updateSliderTrack();
});

function updateSliderTrack() {
    if (!sliderTrack.value) return;
    
    const minValue = parseInt(minPrice.value);
    const maxValue = parseInt(maxPrice.value);
    
    const minPercent = (minValue / 50000) * 100;
    const maxPercent = 100 - (maxValue / 50000) * 100;
    
    sliderTrack.value.style.left = minPercent + '%';
    sliderTrack.value.style.right = maxPercent + '%';
}
</script>

<style scoped>
.price-range {
    padding: 16px 0 32px 0;
    width: 198px;
}

.price-inputs {
    display: flex;
    gap: 12px;
}

.price-input-group {
    position: relative;
    flex: 1;
    color: #707070;
}

.price-input {
    width: 100%;
    height: 36px;
    border: 1px solid #F1F1F1;
    border-radius: 10px;
    padding: 0 32px 0 12px;
    font-size: 14px;
    background: white;
}

.currency-icon {
    position: absolute;
    right: 12px;
    top: 50%;
    transform: translateY(-50%);
    width: 16px;
    height: 16px;
}

.price-input::-webkit-outer-spin-button,
.price-input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

.price-input[type=number] {
    -moz-appearance: textfield;
}

.price-input:focus {
    outline: none;
    border-color: #0075B1;
}

.price-slider {
    position: relative;
    height: 4px;
    background: #E5E5E5;
    border-radius: 1px;
    margin: 20px 0;
    max-width: 198px;
}

.slider-track {
    position: absolute;
    height: 100%;
    background: #0075B1;
    border-radius: 2px;
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
    width: 20px;
    height: 20px;
    background: #F7F7F7;
    border: 3px solid #0075B1;
    border-radius: 4px;
    cursor: pointer;
    pointer-events: all;
}

.slider::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background: #FFFFFF;
    border: 1px solid #E5E5E5;
    border-radius: 4px;
    cursor: pointer;
    pointer-events: all;
}

.slider-min,
.slider-max {
    z-index: 2;
}
</style>