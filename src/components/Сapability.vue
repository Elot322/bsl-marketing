<template>
  <div>
    <p
      class="text-center font-bold mb-[52px] text-4xl">
      Возможности системы
    </p>
    <div
      class="mb-[32px] text-3xl font-semibold">
      <p>Контроль выполнения заявок</p>
      <p>и Планирование ППР</p>
    </div>
    <div
      class="grid grid-cols-2 grid-rows-2 gap-x-5 gap-y-10">
      <div
        class="rounded-lg flex justify-center items-center bg-gradient-to-r from-[#EDFFFD] to-[#65D0C6]">
        <img
          class="mt-[119px] mb-[89px]"
          src="/bsl-laptop.png"/>
      </div>
      <div
        class="grid grid-cols-2 gap-5">
        <CapabilityItem
          v-for="(item, index) in items"
          :key="index"
          :green-mode="greenMode[index]"
          :number="index+1"
          :text="item"/>
      </div>
      <div>

      </div>
      <div>
        <p class="text-3xl font-semibold mb-[32px]">Аналитика</p>
        <div
          class="rounded-lg flex justify-center items-center bg-gradient-to-r from-[#EDFFFD] to-[#65D0C6]">
          <img
            class="mt-[119px] mb-[89px]"
            src="/bsl-laptop-2.png"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import CapabilityItem from './CapabilityItem.vue';

const items = ref([
  'Отслеживание жизненного цикла заявки',
  'Подача  и прием заявки на ремонтные работы',
  'Просмотр истории работ по обслуживанию оборудования',
  'Своевременное выполнения технического обслуживания',
  'Своевременное устранение индидентов и соблюдение SLA',
  'Контроль качества выполнения работ'
])

const greenMode = ref([
  false,
  true,
  true,
  false,
  false,
  true,
])
</script>