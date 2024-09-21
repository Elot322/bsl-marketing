<template>
  <div 
    class="w-full h-[380px] rounded-xl bg-gradient-to-r from-[#3DA096] to-[#79E7DC] relative">
    <div
      class="absolute right-0 top-0">
      <img
        src="/footer-background-up.svg"/>
    </div>
    <div
      class="grid grid-cols-3 gap-24 mt-20 ml-16 text-white">
      <div>
        <img
          src="/logo.svg"/>
        <p
          class="font-semibold mt-5 text-xl">Эксплуатация объектов</p>
        <p
          class="font-semibold text-xl">недвижимости</p>
      </div>
      <div>
        <p
          class="text-2xl mb-6">
          Меню
        </p>
        <p
          class="font-semibold mt-6 text-xl cursor-pointer"
          @click="onLinkClick('interaction')">Функционал</p>
        <p
          class="font-semibold mt-6 text-xl cursor-pointer"
          @click="onLinkClick('effects')">Эффекты</p>
        <p
          class="font-semibold mt-6 text-xl cursor-pointer"
          @click="onAboutAppClick">Возможности системы</p>
        <p
          class="font-semibold mt-6 text-xl cursor-pointer"
          @click="onRPClick">Руководство пользователя</p>
      </div>
      <div>
        <p
          class="text-2xl">Контакты</p>
        <div
          class="flex mt-6 gap-2 items-center">
          <img
            class="w-[24px] h-[24px]"
            src="/footer-mail.svg"/>
          <p
            class="font-semibold text-xl">support@bsl.fm</p>
        </div>
        <div
          class="flex mt-6 gap-2 items-center">
          <img
            class="w-[24px] h-[24px]"
            src="/footer-call.svg"/>
          <p
            class="font-semibold text-xl">+7 (495) 532-02-59</p>
        </div>
      </div>
    </div>
    <div
      class="absolute left-0 bottom-0">
      <img
        src="/footer-background-down.svg"/>
    </div>
  </div>
</template>

<script setup>
const emits = defineEmits(['link-clicked'])

function onLinkClick(name) {
  emits('link-clicked', name)
}

function onAboutAppClick() {
  window.open('https://disk.yandex.ru/i/4zagX_5TMUtUuA', '_blank')
}

function onRPClick() {
  window.open('https://disk.yandex.ru/d/iKCyL-6TREtZLg', '_blank')
}
</script>