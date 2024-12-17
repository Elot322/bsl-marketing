<template>
  <Layout>
    <div
      class="flex flex-col gap-[76px] 2xl:gap-[100px]">
      <div>
        <div
          :class="{
            ['w-[100%] z-[10000] px-2.5 top-0 header']: true,
            ['sticky']: isSticky
          }">
          <Header
            :visibleSection="visibleSection"
            @link-clicked="scrollToLink"/>
        </div>
        <div
          class="mt-3 px-2.5"
          data-section="about"
          ref="about">
          <MainBlock/>
        </div>
      </div>
      <div
        class="px-2.5"
        ref="effects"
        data-section="effects">
        <EffectsBlock/>
      </div>
      <div
        class="px-2.5"
        ref="interaction"
        data-section="interaction">
        <InteractionBlock/>
      </div>
      <div
        class="px-2.5"
        ref="price"
        data-section="price">
        <CalculateBlock/>
      </div>
      <div
        class="px-2.5"
        ref="footer"
        data-section="footer">
        <Footer
          @link-clicked="scrollToLink"/>
      </div>
    </div>
  </Layout>
</template>

<script setup>
import { ref, computed, onMounted, onBeforeUnmount, onBeforeMount} from 'vue'

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

const visibleSection = ref('');

const checkVisibleSection = () => {
      const scrollY = window.scrollY;

      for (const key in refs.value) {
        const section = refs.value[key];
        if (section) {
          const rect = section.value.getBoundingClientRect();
          if (rect.top <= window.innerHeight / 2 && rect.bottom >= window.innerHeight / 2) {
            if (visibleSection.value !== section.value.getAttribute('data-section')) {
              visibleSection.value = section.value.getAttribute('data-section');
              console.log(visibleSection.value)
            }
          }
        }
      }
    };

async function scrollToLink(name) {
  const element = refs.value[name]?.value;

  if (element) {
    const top = element.offsetTop;
    window.scrollTo({ top, behavior: 'smooth' });
  } 
}

const isSticky = ref(false);
const lastScrollY = ref(0);

const handleScroll = () => {
  checkVisibleSection()
  const scrollY = window.scrollY;

  // Проверяем, если прокрутка больше 100 пикселей
  if (scrollY > 100) {
    isSticky.value = true; // Делаем шапку "липкой"
  } else {
    isSticky.value = false; // Скрываем шапку, если прокрутка меньше 100 пикселей
  }

  lastScrollY.value = scrollY;
};

onMounted(async () => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.header {
  transition: transform 0.5s ease; /* Плавный переход для transform и background-color */
}

.header:not(.sticky) {
  transform: translateY(0); /* Сдвигаем заголовок вверх, когда он не фиксирован */
}
.sticky {
  transform: translateY(5%);
  position: fixed;
  top: 0;
  width: 100%;
}
</style>
