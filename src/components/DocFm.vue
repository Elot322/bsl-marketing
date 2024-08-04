<template>
  <div
    class="grid grid-cols-2 gap-5">
    <div
      class="card-item-left rounded-lg py-8 p-9 flex flex-col justify-between">
      <div>
        <p class="text-4xl mb-5">Doc FM</p>
        <p class="w-[484px] font-semibold text-2xl">Упрощенный сервис для сбора заявок от арендаторов или сотрудников эксплуатируемого здания</p>
      </div>
      <div
        class="flex flex-col gap-4">
        <DocFmItem
          v-for="(item, index) in items"
          :key="index"
          :text="item"/>
      </div>
    </div>
    <div
      class="card-item-right rounded-lg flex justify-center items-center py-8">
      <img
        src="/docfm-phone.png"/>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import DocFmItem from './DocFmItem.vue';

const items = ref([
  'Просмотр статуса выполнения работ',
  'Внутренний функционал считывания QR-кодов'
])
</script>

<style scoped>
.card-item-left {
  background: 
    linear-gradient(303.75deg, #B9F6F199 25.51%, #CAD0FF 74.94%),
    linear-gradient(113.13deg, rgba(255, 255, 255, 0.6) 18.49%, rgba(185, 246, 241, 0.6) 75.69%);
}

.card-item-right {
  background: 
    linear-gradient(113.75deg, #B9F6F199 25.51%, #CAD0FF 74.94%),
    linear-gradient(303.13deg, rgba(255, 255, 255, 0.6) 18.49%, rgba(185, 246, 241, 0.6) 75.69%);
}
</style>