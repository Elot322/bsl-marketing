<template>
  <div class="w-[268px]">
    <div
      class="w-[56px] h-[56px] p-4 bg-gradient-to-r from-[#A3F2EA] to-[#51B2A9] rounded-lg">
      <img
        :src="imgUrl"/>
    </div>
    <div
      class="mt-5">
      <p
        class="text-black font-semibold">
        {{ text }}
      </p>
    </div>
  </div>
</template>

<script setup>
defineProps(['imgUrl', 'text'])

</script>