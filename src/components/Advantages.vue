<template>
  <div>
    <div
      class="mb-[50px]">
      <p
        class="font-bold text-4xl text-center">
        Преимущества использования
      </p>
      <p
        class="font-bold text-4xl text-center">
        комплексного сервиса
      </p>
    </div>
    <div
      class="grid grid-cols-3 gap-5">
      <AdvantagesItem
        v-for="(item, index) in items"
        :key="index"
        :icon="item.urlImage"
        :text="item.text"/>
    </div>
    <div
      class="grid grid-cols-2 gap-5 mt-5">
      <AdvantagesCircleItem
        v-for="(item, index) in itemsCircle"
        :key="index"
        :title="item.title"
        :text="item.text"
        :image="item.urlImage"/>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import AdvantagesItem from './AdvantagesItem.vue'
import AdvantagesCircleItem from './AdvantagesCircleItem.vue'

const items = ref([
  {
    urlImage: '/advantages-discovery.svg',
    text: 'Единый сервисный подход'
  },
  {
    urlImage: '/advantages-arrow-up.svg',
    text: 'Повышение качества обслуживания ОКС'
  },
  {
    urlImage: '/advantages-arrow-down.svg',
    text: 'Снижение расходов эксплуатации'
  }
])

const itemsCircle = ref([
  {
    title: '-15%',
    text: 'Снижение затрат на материалы',
    urlImage: '/advantages-circle-left.svg'
  },
  {
    title: '-50%',
    text: 'Сокращение времени простоя оборудования',
    urlImage: '/advantages-circle-right.svg'
  }
])
</script>