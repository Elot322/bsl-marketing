<template>
  <div
    ref="container"
    class="w-full relative overflow-hidden">
    <div
      class="absolute top-64 right-2px">
      <img
        :width="containerWidth"
        src="/for-whom-background.svg"/>
    </div>
    <p
      class="text-center font-bold mb-[52px] text-4xl">Для кого</p>
    <div
      class="grid grid-cols-3 gap-5">
      <ForWhomItem
        v-for="(item, index) in items"
        :key="index"
        :text="item"/>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

import ForWhomItem from './ForWhomItem.vue';

const container = ref(null);
const containerWidth = ref(0);

function updateWidth() {
  if (container.value) {
    containerWidth.value = container.value.clientWidth + 10;
    console.log(containerWidth)
  }
};

onMounted(() => {
  updateWidth();

  const resizeObserver = new ResizeObserver(updateWidth);
  resizeObserver.observe(container.value);

  onBeforeUnmount(() => {
    resizeObserver.disconnect();
  });
});

const items = [
  'Собственники недвижимости',
  'Управляющая компания',
  'Служба эксплуатации'
]


</script>