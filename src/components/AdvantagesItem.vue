<template>
  <div
    class="flex gap-4 items-center border-2 border-black px-5 py-7 rounded-xl">
    <img
      :src="icon"/>
    <p
      class="text-2xl font-semibold">
      {{ text }}
    </p>
  </div>
</template>

<script setup>
defineProps(['text', 'icon'])
</script>