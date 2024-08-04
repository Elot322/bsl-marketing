<template>
  <div
    class="h-[364px] bg-gradient-to-r from-[#6BD8CE] to-[#3FA49A] rounded-lg">
    <div
      class="mt-7 ml-7 w-[260px] text-2xl text-white">
      {{ text }}
    </div>
  </div>
</template>

<script setup>
defineProps(['text'])
</script>