<template>
  <div
    class="p-[22px] rounded-xl bg-white">
    <div
      class="flex items-center justify-between">
      <div>
        <slot name="first"></slot>
      </div>
      <div>
        <slot name="second"></slot>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps(['reversed'])
</script>

<style module>

</style>