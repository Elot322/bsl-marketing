<template>
  <div class="flex gap-2 items-center px-7 py-4 border-2 border-black rounded-lg w-fit">
    <img
      src="/docfm-stars.svg"/>
    <p>{{ text }}</p>
  </div>
</template>

<script setup>
defineProps(['text'])
</script>