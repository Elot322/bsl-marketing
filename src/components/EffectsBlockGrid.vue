<template>
  <div
    class="grid grid-cols-2 grid-rows-2 gap-5">
    <EffectsBlockGridItem
      v-for="(item) in effectsBlockItems"
      :title="item.title"
      :description="item.description"
      :icon="item.icon"/>
  </div>
</template>

<script setup>
import EffectsBlockGridItem from './EffectsBlockGridItem.vue'

import { ref } from 'vue'

const effectsBlockItems = ref([
  {
    title: 'Временной',
    description: 'Сокращение времени простоя оборудования',
    icon: '/effects-block-clock.svg'
  },
  {
    title: 'Единая среда управления',
    description: 'Принятие оптимальных управленческих решений',
    icon: '/effects-block-computer.svg'
  },
  {
    title: 'Финансовый',
    description: 'Оптимизация затрат на обслуживание оборудования',
    icon: '/effects-block-wallet.svg'
  },
  {
    title: 'SLA',
    description: 'Постоянное увеличение эффективности',
    icon: '/effects-block-document.svg'
  }
])
</script>