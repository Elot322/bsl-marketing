<template>
  <div>
    <p
      class="text-center text-4xl mb-[44px]">
      Взаимодействие с системой
    </p>
    <div>
      <IteractionBlockItem>
        <template #first>
          <p
            class="text-4xl">Помогаем управлять объектами недвижимости</p>
          <div
            class="mt-8">
            <p
              class="text-2xl">Функциональность системы</p>
            <ul class="mt-5 font-medium">
              <li class="text-xl"><span class="font-bold text-2xl">•</span> Создание проекта и ОКС</li>
              <li class="text-xl"><span class="font-bold text-2xl">•</span> Планирование работ по техобслуживанию</li>
              <li class="text-xl"><span class="font-bold text-2xl">•</span> Отслеживание статуса выполнения работ</li>
              <li class="text-xl"><span class="font-bold text-2xl">•</span> Анализ качества выполненных работ</li>
            </ul>
          </div>
        </template>
        <template #second>
          <div
            class="w-[556px] h-[482px] customGradientContainer rounded-xl relative">
            <div
              class="absolute bottom-0 right-0">
              <img
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
              class="w-[556px] h-[482px] customGradientContainer rounded-xl relative">
              <div
                class="absolute bottom-0 right-0">
                <img
                  src="/interaction-block-iphone.svg"/>
              </div>
            </div>
          </div>
          <div>
            <p
              class="text-4xl max-w-[529px]">Собираем заявки от гостей и сотрудников</p>
            <div
              class="mt-8">
              <p
                class="text-2xl max-w-[452px]">Для сотрудников эксплуатирующей компании</p>
              <ul class="mt-5 font-medium">
                <li class="text-xl"><span class="font-bold text-2xl">•</span> Работа с заявками</li>
                <li class="text-xl"><span class="font-bold text-2xl">•</span> Отслеживание назначенных заявок</li>
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