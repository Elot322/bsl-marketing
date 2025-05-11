<template>
  <div 
    class="w-full rounded-xl bg-gradient-to-r from-[#3DA096] to-[#79E7DC] relative z-0">
    <div
      class="absolute right-0 top-0 z-0">
      <img
        class="2xl:w-[1500px]"
        src="/footer-background-up.svg"/>
    </div>
    <div
      class="grid grid-cols-3 gap-24 mt-14 ml-16 mb-5 relative z-10 text-white">
      <div>
        <img
          src="/logo.svg"/>
        <p
          class="font-semibold mt-5 text-xl 2xl:text-2xl">Эксплуатация объектов</p>
        <p
          class="font-semibold text-xl 2xl:text-2xl">недвижимости</p>
      </div>
      <div
        class="z-10">
        <p
          class="text-2xl 2xl:text-3xl mb-6">
          Меню
        </p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onLinkClick('interaction')">Функционал</p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onLinkClick('effects')">Эффекты</p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onAboutAppClick">Описание функциональных характеристик</p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onRPClick">Руководство пользователя</p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onPolicClick">Политика конфиденциальности</p>
        <p
          class="font-semibold mt-3 text-xl cursor-pointer"
          @click="onDataClick">Согласие на обработку персональных данных</p>
      </div>
      <div>
        <p
          class="text-2xl 2xl:text-3xl">Контакты</p>
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
        <div
          class="mt-6 font-semibold text-xl">
          <p>ООО «АЛМАТЭК»</p>
          <p>ОГРН: 1257700085500</p>
          <p>ИНН: 9725180163</p>
        </div>
      </div>
    </div>
    <div
      class="absolute left-0 bottom-0">
      <img
        class="2xl:w-[900px]"
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
  window.open('/Описание функциональных характеристик (ПО Building Service Life).pdf', '_blank')
}

function onRPClick() {
  window.open('/Руководство_пользователя_ПО_Building_Service_Life.pdf', '_blank')
}

function onPolicClick() {
  window.open('/Политика конфиденциальности в отношении обработки персональных данных.pdf', '_blank')
}

function onDataClick() {
  window.open('/Согласие на обработку персональных данных.pdf', '_blank')
}
</script>