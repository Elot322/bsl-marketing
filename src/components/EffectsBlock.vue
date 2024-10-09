<template>
  <div>
    <p
      class="text-center text-4xl 2xl:text-[52px] 2xl:leading-normal mb-[44px]">
      Эффекты
    </p>
    <div>
      <EffectsBlockGrid/>
    </div>
    <div
      class="mt-5">
      <EffectsBlockNumbers/>
    </div>
  </div>
</template>

<script setup>
import EffectsBlockGrid from './EffectsBlockGrid.vue';
import EffectsBlockNumbers from './EffectsBlockNumbers.vue';
</script>