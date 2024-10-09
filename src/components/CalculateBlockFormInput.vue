<template>
  <div>
    <label :for="name" class="block text-[22px] 2xl:text-[24px] font-medium">{{ label }}</label>
    <input 
      type="text" 
      id="name" 
      class="text-[22px] 2xl:text-[24px] font-normal outline-0 bg-white border border-black focus:border-2 focus:ring-black focus:border-black text-black text-sm rounded-md block w-full p-4" 
      :placeholder="placeholder"
      v-model="model"/>
  </div>
</template>

<script setup>
defineProps(['label', 'name', 'placeholder'])
const model = defineModel()

</script>

<style>
</style>

