<template>
  <div
    class="w-full flex justify-center py-[90px]">
    <div
      class="flex gap-16">
      <MainAboutCompanyItem
        v-for="(item, index) in items"
        :key="index"
        :img-url="item.imgUrl"
        :text="item.text"
      />
    </div>
  </div>
</template>

<script setup>
import MainAboutCompanyItem from './MainAboutCompanyItem.vue';

const items = [
  {
    imgUrl: '/about-circle.svg',
    text: 'Управление жизненным циклом объекта недвижимости'
  },
  {
    imgUrl: '/about-success.svg',
    text: 'Контроль выполнения заявок'
  },
  {
    imgUrl: '/about-recent.svg',
    text: 'Своевременное обслуживание оборудования'
  }
]

</script>