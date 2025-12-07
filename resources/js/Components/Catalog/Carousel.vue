<template>
    <div class="flex gap-5">
        <div class="flex flex-col items-center">
            <button type="button" 
                    @click="scrollUp"
                    class="mb-5">
                <img src="/image/top.svg"
                     alt="Up" />
            </button>
            
            <div>
                <div v-for="(image, index) in images" 
                     :key="index"
                     @click="selectImage(index)"
                     :class="['cursor-pointer mb-3  border-2 w-[86px] h-[86px] rounded-[5px]',
                             currentIndex === index 
                                ? 'border-[#006598]' 
                                : 'border-[#e1e1e1]']">
                    <div class="relative w-full h-full flex items-center justify-center">
                        <!-- Image -->
                        <img :src="image" 
                             class="w-[86px] h-[86px] rounded-[5px] max-w-full max-h-full object-contain"
                             :alt="`Thumb ${index + 1}`" />
                    </div>
                </div>
            </div>
            
            <button type="button" 
                    @click="scrollDown"
                    class="mt-3">
                <img src="/image/bottom.svg"
                     alt="Down" />
            </button>
        </div>

        <div class="flex-1">
            <div class=" flex items-center justify-center">
                <img :src="images[currentIndex]" 
                     class="h-[540px] max-w-full max-h-full object-contain"
                     :alt="`Main image`" />
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const currentIndex = ref(0)
const images = [
    '/image/carousel1.svg',
    '/image/carousel2.svg',
    '/image/carousel3.svg',
    '/image/carousel4.svg',
    '/image/carousel5.svg'
]

const selectImage = (index) => {
    currentIndex.value = index
}

const scrollUp = () => {
    currentIndex.value = currentIndex.value > 0 ? currentIndex.value - 1 : images.length - 1
}

const scrollDown = () => {
    currentIndex.value = currentIndex.value < images.length - 1 ? currentIndex.value + 1 : 0
}
</script>