<template>
  <div
    class="border-2 border-black rounded-xl flex flex-col justify-center items-center">
    <div
      class="relative mt-9">
      <img
        :src="image"/>
      <p 
        class="text-8xl font-semibold absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
        {{ title }}
      </p>
    </div>
    <p
      class="text-center w-[232px] text-2xl my-10">
      {{ text }}
    </p>
  </div>
</template>

<script setup>
defineProps(['text', 'image', 'title'])

</script>