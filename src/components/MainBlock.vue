<template>
  <div
    class="h-[600px] 2xl:h-[640px] rounded-xl bg-gradient-to-r from-[#2A8A81] to-[#79E7DC] relative">
    <div
      class="absolute right-0 bottom-0">
      <img
        class="2xl:w-[1600px] 2xl:h-[700px]"
        src="/main-block-abstraction.svg"/>
    </div>
    <div
      class="absolute right-0 bottom-[20px]">
      <img
        class="2xl:w-[940px] 2xl:h-[516px]"
        src="/main-block-macbook.svg"/>
    </div>
    <div
      class="absolute right-[400px] bottom-0 2xl:right-[600px]">
      <img
        class="2xl:w-[192px] 2xl:h-[290px]"
        src="/main-block-iphone.svg"/>
    </div>
    <div
      class="text-white text-[44px] ml-10 mt-[146px] 2xl:text-[64px]">
      <div
        class="w-fit">
        <p class="overflow-hidden">Сервис для цифровой</p>
        <p class="overflow-hidden py-2">эксплуатации</p>
        <p class="overflow-hidden">объектов недвижимости</p>
      </div>
      <div 
        @click="onAuthClick"
        class="rounded-lg px-10 py-5 text-2xl 2xl:text-3xl text-center mt-[48px] bg-white text-[#27AEA2] cursor-pointer w-fit">
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