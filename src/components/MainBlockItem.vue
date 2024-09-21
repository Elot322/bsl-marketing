<template>
  <div
    class="flex gap-3 w-fit">
    <div>
      <img
        :src="icon"/>
    </div>
    <div
      class="w-fit text-2xl">
      <p>{{ titleFor }}</p>
      <p>{{ titleWho }}</p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(['icon', 'titleFor', 'titleWho'])
</script>