<template>
  <div>
    <p
      class="text-center text-4xl 2xl:text-[52px] 2xl:leading-normal mb-[44px]">
      Взаимодействие с системой
    </p>
    <div>
      <IteractionBlockItem>
        <template #first>
          <p
            class="text-4xl 2xl:text-5xl 2xl:leading-normal 2xl:max-w-[669px]">Помогаем управлять объектами недвижимости</p>
          <div
            class="mt-8">
            <p
              class="text-2xl 2xl:text-3xl">Функциональность системы</p>
            <ul class="mt-5 font-medium">
              <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Создание проекта и ОКС</li>
              <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Планирование работ по техобслуживанию</li>
              <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Отслеживание статуса выполнения работ</li>
              <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Анализ качества выполненных работ</li>
            </ul>
          </div>
        </template>
        <template #second>
          <div
            class="w-[556px] h-[482px] 2xl:w-[916px] 2xl:h-[597px] customGradientContainer rounded-xl relative">
            <div
              class="absolute bottom-0 right-0">
              <img
                class="2xl:w-[916px] 2xl:h-[500px]"
                src="/interaction-block-macbook.svg"/>
            </div>
          </div>
        </template>
      </IteractionBlockItem>
    </div>
    <div
      class="mt-5">
      <div
        class="bg-white rounded-xl p-5">
        <div
          class="flex flex-start items-center gap-8">
          <div>
            <div
              class="w-[556px] h-[482px] 2xl:w-[916px] 2xl:h-[564px] customGradientContainer rounded-xl relative">
              <div
                class="absolute bottom-0 right-0">
                <img
                  class="2xl:w-[916px] 2xl:h-[500px]"
                  src="/interaction-block-iphone.svg"/>
              </div>
            </div>
          </div>
          <div>
            <p
              class="text-4xl max-w-[529px] 2xl:text-5xl 2xl:leading-normal 2xl:max-w-[785px]">Собираем заявки от гостей и сотрудников</p>
            <div
              class="mt-8">
              <p
                class="text-2xl max-w-[452px] 2xl:text-3xl">Для сотрудников эксплуатирующей компании</p>
              <ul class="mt-5 font-medium">
                <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Работа с заявками</li>
                <li class="text-xl 2xl:text-2xl"><span class="font-bold text-2xl">•</span> Отслеживание назначенных заявок</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import IteractionBlockItem from './IteractionBlockItem.vue'

</script>

<style scoped>
.customGradientContainer {
  background: 
    linear-gradient(-245.96deg, rgba(255, 255, 255, 0.8) -1.57%, rgba(147, 209, 202, 0.8) 55.3%),
    linear-gradient(-182.74deg, #EDFFFD 16.55%, #65D0C6 129.61%);
}
</style>182.74deg