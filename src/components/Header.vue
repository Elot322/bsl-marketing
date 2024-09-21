<template>
  <div
    class="mt-2 w-full flex content-center h-[87px] rounded-xl bg-gradient-to-r from-[#2A8A81] to-[#79E7DC]">
    <div
      class="w-full flex justify-between items-center px-4">
      <img
        width="109"
        height="44"
        src="/logo.svg"/>
      <div
        class="flex gap-6 items-center text-base">
        <div
          class="flex gap-5 items-center text-base">
          <p 
            class="text-white cursor-pointer"
            @click="onLinkClick('about')">О продукте</p>
          <p 
            class="text-white cursor-pointer"
            @click="onLinkClick('effects')">Эффекты</p>
          <p 
            class="text-white cursor-pointer"
            @click="onLinkClick('interaction')">Взаимодействие</p>
          <p 
            class="text-white cursor-pointer"
            @click="onLinkClick('price')">Стоимость</p>
        </div>
        <div
          class="flex gap-3">
          <div
            class="py-3 px-5 text-center border-[1.4px] border-white rounded-md cursor-pointer text-base text-white hover:bg-[#ffffff28]"
            @click="onAuthClick">
            <p>Авторизироваться</p>
          </div>
          <div
            class="px-5 py-3 text-center border-[1.4px] border-white bg-white hover:bg-[#27AEA2] rounded-md cursor-pointer text-base text-[#27AEA2] hover:text-white"
            @click="onLinkClick('footer')">
            <p>Связаться с нами</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const emits = defineEmits(['link-clicked'])

function onLinkClick(name) {
  emits('link-clicked', name)
}

function onAuthClick() {
  window.open('https://bsl.fliptap.ru/auth/sign-in', '_blank')
}

</script>
