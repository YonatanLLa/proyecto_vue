<script setup lang="ts">
import AppHome from "./components/AppHome.vue";
import BentoGrid from "./components/BentoGrid.vue";
import AppCarrusel from "./components/AppCarrusel.vue";
// import BentoGridThree from "./components/BentoGridThree.vue";
</script>

<template>
  <div>
    <div class="relative">
      <div
        class="absolute z-50 top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 flex items-center justify-center gap-2 flex-col w-full"
      >
        <h1 class="lg:text-8xl text-center p-2 text-5xl font-bold text-white">
          FELIZ CUMPLEAÑOS ZOE 🎉
        </h1>
        <p class="text-white text-center lg:text-4xl text-2xl p-2">
          Espero que hoy sea un día increíble, te amo muchisimo ❤️.
        </p>
      </div>
      <AppHome />
    </div>
  </div>
  <AppCarrusel />
  <BentoGrid />
  <div class="bg-black text-white h-full w-full">
    <h2 class="text-3xl text-center py-4">
      La vida está llena de cosas bonitas, por ejemplo, tú
    </h2>
  </div>
  <!-- <BentoGridThree /> -->
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
