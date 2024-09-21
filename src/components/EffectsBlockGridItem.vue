<template>
  <div
    class="p-6 bg-white rounded-[12px]">
    <div
      class="flex gap-5 items-center">
      <div
        class="p-[30px] rounded-lg bg-gradient-to-r from-[#8AD6CF] to-[#48B1A7]">
        <img
          :src="icon"/>
      </div>
      <div>
        <p class="text-2xl text-[#262626]">{{ title }}</p>
        <p class="text-xl text-[#262626] font-medium max-w-[400px]">{{ description }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps(['icon', 'title', 'description'])
</script>