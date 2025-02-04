<script setup lang="ts">
import { ref, onMounted, onUnmounted } from "vue";

const images = ref([
  "/carrusel_1.png",
  "/carrusel_2.png",
  "/carrusel_3.png",
  "/perfil_7.jpeg",
  "/perfil_8.jpeg",
]);

const currentIndex = ref(0);
const isHovered = ref(false);
const intervalId = ref<number | null | undefined>(null);
const isTransitioning = ref(false);

const nextSlide = () => {
  if (isTransitioning.value) return;
  isTransitioning.value = true;

  setTimeout(() => {
    currentIndex.value = (currentIndex.value + 1) % images.value.length;
    isTransitioning.value = false;
  }, 300);
};

const startAutoplay = () => {
  intervalId.value = setInterval(() => {
    if (!isHovered.value) nextSlide();
  }, 3000);
};

const stopAutoplay = () => {
  if (intervalId.value !== null) {
    clearInterval(intervalId.value);
  }
};

onMounted(() => startAutoplay());
onUnmounted(() => stopAutoplay());

// Swipe en móviles
let startX = 0;
const onTouchStart = (e: TouchEvent) => (startX = e.touches[0].clientX);
const onTouchEnd = (e: TouchEvent) => {
  const deltaX = e.changedTouches[0].clientX - startX;
  if (deltaX > 50)
    currentIndex.value =
      (currentIndex.value - 1 + images.value.length) % images.value.length;
  if (deltaX < -50) nextSlide();
};
</script>

<template>
  <div
    class="relative w-full h-screen overflow-hidden"
    @mouseenter="isHovered = true"
    @mouseleave="isHovered = false"
    @touchstart="onTouchStart"
    @touchend="onTouchEnd"
  >
    <!-- Carrusel -->
    <div
      class="flex transition-transform duration-500 ease-in-out"
      :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
    >
      <div v-for="(img, index) in images" :key="index" class="min-w-full">
        <img :src="img" class="w-full h-screen object-cover" alt="" />
      </div>
    </div>

    <!-- Indicadores -->
    <div class="absolute bottom-4 left-1/2 -translate-x-1/2 flex space-x-2">
      <span
        v-for="(_img, index) in images"
        :key="index"
        @click="currentIndex = index"
        class="w-3 h-3 rounded-full cursor-pointer transition-all"
        :class="index === currentIndex ? 'bg-white scale-110' : 'bg-gray-500'"
      >
      </span>
    </div>
  </div>
</template>
