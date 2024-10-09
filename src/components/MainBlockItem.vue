<template>
  <div
    class="flex gap-3 w-fit items-center">
    <div>
      <img
        class="2xl:w-[64px] 2xl:h-[64px]"
        :src="icon"/>
    </div>
    <div
      class="w-fit text-2xl 2xl:text-3xl">
      <p>{{ titleFor }}</p>
      <p>{{ titleWho }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['icon', 'titleFor', 'titleWho'])
</script>