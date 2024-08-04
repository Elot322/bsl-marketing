<template>
  <div
    class="mt-2 w-full flex content-center h-[87px] rounded-xl bg-gradient-to-r from-[#2A8A81] to-[#79E7DC]">
    <div
      class="w-full flex justify-between items-center px-4">
      <img
        width="136"
        height="55"
        src="/logo.svg"/>
      <div
        class="flex gap-10 items-center text-base">
        <p 
          class="text-white cursor-pointer"
          @click="onLinkClick('about')">О продукте</p>
        <p 
          class="text-white cursor-pointer"
          @click="onLinkClick('capability')">Преимущества</p>
        <p 
          class="text-white cursor-pointer"
          @click="onLinkClick('users')">Пользователи</p>
        <p 
          class="text-white cursor-pointer"
          @click="onLinkClick('contacts')">Контакты</p>
        <div
          class="flex justify-center items-center bg-white rounded-xl h-[51px] w-[220px] cursor-pointer text-[#228178]">
          Связаться с нами
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

</script>
