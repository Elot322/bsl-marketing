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
      <!-- Баннер о куках -->
      <div v-if="showCookieBanner" class="cookie-banner">
      <p>
        Мы используем <span class="underline cursor-pointer" @click="onCookieClick">файлы cookie</span> в системе BSL, чтобы делать ее лучше для Вас
      </p>
      <button @click="acceptCookies">Понятно</button>
    </div>
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

function onCookieClick() {
  window.open('/Политика_конфиденциальности_в_отношении_обработки_персональных_данных.pdf', '_blank')
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

const showCookieBanner = ref(false)

onMounted(async () => {
  window.addEventListener('scroll', handleScroll);
  const cookiesAccepted = localStorage.getItem('cookiesAccepted');
  if (!cookiesAccepted) {
    console.log(cookiesAccepted)
    showCookieBanner.value = true; // Показываем баннер, если куки еще не приняты
  }
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});

function acceptCookies() {
  localStorage.setItem('cookiesAccepted', 'true'); // Сохраняем флаг принятия куков
  showCookieBanner.value = false; // Скрываем баннер
}
</script>

<style scoped>
.header {
  transition: transform 0.5s ease; /* Плавный переход для transform и background-color */
}

.cookie-banner {
  position: fixed;
  bottom: 30px;
  left: 0;
  right: 0;
  background-color: #333333D9;
  border-radius: 8px;
  max-width: 70vw;
  margin: 0 auto;
  color: #fff;
  padding: 15px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
  z-index: 9999; /* Чтобы баннер был поверх всего */
}

.cookie-banner button {
  background-color: #F2F4F7;
  color: #28282D;
  border: none;
  padding: 8px 16px;
  cursor: pointer;
  border-radius: 6px;
  transition: background-color 0.3s ease;
}

.cookie-banner button:hover {
  background-color: #c4c4c4;
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
