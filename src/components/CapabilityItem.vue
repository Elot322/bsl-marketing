<template>
  <div
    :class="{
      ['default']: true,
      ['card']: !greenMode,
      ['greenCard']: greenMode
    }">
    <div
      :class="{
        ['mt-4 ml-4']: true,
        ['number']: !greenMode,
        ['greenNumber']: greenMode
      }">
      0{{ number }}
    </div>
    <div
      :class="{
        ['mt-3 ml-4 w-[226px]']: true,
        ['text']: !greenMode,
        ['greenText']: greenMode
      }">
      {{ text }}
    </div>
  </div>
</template>

<script setup>
defineProps(['greenMode', 'number', 'text'])
</script>

<style scoped>
.default {
  @apply rounded-lg;
}

.card {
  @apply border-2 border-black;
}

.greenCard {
  @apply border-0 bg-[#65D0C6];
}

.number {
  @apply text-3xl font-semibold text-[#65D0C6];
}

.greenNumber {
  @apply text-3xl font-semibold text-white;
}

.text {
  @apply text-black;
}

.greenText {
  @apply text-white;
}
</style>