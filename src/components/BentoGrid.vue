<script setup lang="ts"></script>
<template>
  <div class="">
    <div class="grid grid-cols-2">
      <div>
        <img v-lazy="'../../public/perfil_6.jpeg'" alt="" />
        <img v-lazy="'../../public/perfil_3.jpeg'" alt="" />
      </div>
      <div class="">
        <img
          class="w-full h-full object-cover"
          v-lazy="'../../public/perfil_5.jpeg'"
          alt=""
        />
      </div>
      <img
        class="w-full h-full object-cover"
        v-lazy="'../../public/perfil_1.jpeg'"
        alt=""
      />
      <img
        class="w-full h-full object-cover"
        v-lazy="'../../public/perfil_2.jpeg'"
        alt=""
      />
      <img
        class="w-full h-full object-cover"
        v-lazy="'../../public/perfil_4.jpeg'"
        alt=""
      />
      <img
        class="w-full h-full object-cover"
        v-lazy="'../../public/perfil_9.jpg'"
        alt=""
      />
    </div>
  </div>
</template>
