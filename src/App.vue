<template>
  <Layout>
    <div
      class="flex flex-col gap-[76px]">
      <div>
        <Header
          @link-clicked="scrollToLink"/>
        <div
          class="mt-3"
          ref="about">
          <MainBlock/>
        </div>
      </div>
      <div
        ref="effects">
        <EffectsBlock/>
      </div>
      <div
        ref="interaction">
        <InteractionBlock/>
      </div>
      <div
        ref="price">
        <CalculateBlock/>
      </div>
      <div
        ref="footer">
        <Footer
          @link-clicked="scrollToLink"/>
      </div>
    </div>
  </Layout>
</template>

<script setup>
import { ref, computed } from 'vue'

import Layout from './components/Layout.vue'
import Header from './components/Header.vue'
import MainBlock from './components/MainBlock.vue'
import EffectsBlock from './components/EffectsBlock.vue'
import InteractionBlock from './components/InteractionBlock.vue'
import CalculateBlock from './components/CalculateBlock.vue'
import Footer from './components/Footer.vue'

// Определяем рефы для компонентов
const about = ref(null)
const effects = ref(null)
const interaction = ref(null)
const price = ref(null)
const footer = ref(null)

const refs = computed( () => {
  return {
    about,
    effects,
    interaction,
    price,
    footer
  }
});

async function scrollToLink(name) {
  const element = refs.value[name]?.value;

  if (element) {
    const top = element.offsetTop;
    window.scrollTo({ top, behavior: 'smooth' });
  } 
}
</script>

<style scoped>

</style>
