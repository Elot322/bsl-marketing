<template>
  <div>
    <p
      class="text-center text-4xl 2xl:text-[52px] 2xl:leading-normal mb-[44px]">
      Рассчитать стоимость ПО
    </p>
    <div
      class="rounded-xl bg-[#46BFB3] flex justify-between p-6 relative">
      <p
        class="text-2xl 2xl:text-3xl text-white w-[467px] 2xl:w-[696px]">
        Стоимость определяется индивидуально для каждого из запросов
      </p>
      <img
        class="absolute bottom-0 left-0 2xl:left-0 2xl:h-[400px]"
        src="/calculate-block-circle-left.svg"/>
      <img
        class="absolute top-0 right-0 h-full 2xl:right-80"
        src="/calculate-block-circle-right.svg"/>
      <div
        class="absolute">
        <img/>
      </div>
      <CalculateBlockForm
        v-if="!isSended"
        @request:sended="onRequestSended"
        class="z-10"/>
      <CalculateBlockFormSuccess
        v-else
        class="z-10"/>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

import CalculateBlockForm from './CalculateBlockForm.vue'
import CalculateBlockFormSuccess from './CalculateBlockFormSuccess.vue'

const isSended = ref(false)

function onRequestSended() {
  isSended.value = true
}
</script>