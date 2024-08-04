<template>
  <Layout>
    <div
      class="w-full flex flex-col gap-16 mb-5">
      <Header
        @link-clicked="scrollToLink"/>
      <div
        ref="about">
        <MainBlock/>
      </div>
        <MainAboutCompany/>
      <div
        ref="users">
        <ForWhom/>
      </div>
      <div
        ref="capability">
        <Capability/>
      </div>
      <DocFm/>
      <Advantages/>
      <div
        ref="contacts">
        <Footer/>
      </div>
    </div>
  </Layout>
</template>

<script setup>
import { ref, computed, nextTick, onMounted } from 'vue'

import Layout from './components/Layout.vue'
import Header from './components/Header.vue'
import MainBlock from './components/MainBlock.vue'
import MainAboutCompany from './components/MainAboutCompany.vue'
import ForWhom from './components/ForWhom.vue'
import Capability from './components/Сapability.vue'
import DocFm from './components/DocFm.vue'
import Advantages from './components/Advantages.vue'
import Footer from './components/Footer.vue'

// Определяем рефы для компонентов
const about = ref(null)
const users = ref(null)
const capability = ref(null)
const contacts = ref(null)

const refs = computed( () => {
  return {
    about,
    users,
    capability,
    contacts
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
