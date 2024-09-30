<template>
  <div
    class="h-[600px] rounded-xl bg-gradient-to-r from-[#2A8A81] to-[#79E7DC] relative">
    <div
      class="absolute right-0">
      <img
        src="/main-block-abstraction.svg"/>
    </div>
    <div
      class="absolute right-0 bottom-[20px]">
      <img
        src="/main-block-macbook.svg"/>
    </div>
    <div
      class="absolute right-[400px] bottom-0">
      <img
        src="/main-block-iphone.svg"/>
    </div>
    <div
      class="text-white text-[44px] ml-10 mt-[146px]">
      <div
        class="w-fit">
        <p class="overflow-hidden">Сервис для цифровой</p>
        <p class="overflow-hidden py-2">эксплуатации</p>
        <p class="overflow-hidden">объектов недвижимости</p>
      </div>
      <div 
        @click="onAuthClick"
        class="rounded-lg px-10 py-5 text-2xl text-center mt-[48px] bg-white text-[#27AEA2] cursor-pointer w-fit">
        Авторизироваться в BSL
      </div>
    </div>
  </div>
  <div
    class="rounded-xl bg-white grid grid-cols-3 divide-x py-7 px-7 mt-3">
    <div class="w-full flex justify-center">
    <MainBlockItem
      titleFor="Для управляющих"
      titleWho="компаний"
      icon="/main-block-for-company.svg"/>
    </div>
    <div class="w-full flex justify-center">
    <MainBlockItem
      class="place-self-center"
      titleFor="Для собственников"
      titleWho="недвижимости"
      icon="/main-block-for-owner.svg"/>
    </div>
    <div class="w-full flex justify-center">
    <MainBlockItem
      titleFor="Для службы"
      titleWho="эксплуатации"
      icon="/main-block-for-managment.svg"/>
    </div>
  </div>
</template>

<script setup>
import MainBlockItem from './MainBlockItem.vue'

function onAuthClick() {
  window.open('https://app.bsl.fm/auth/sign-in', '_blank')
}
</script>