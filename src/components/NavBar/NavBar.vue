<template>
  <div :class="[$style['nav-bar'], isMenuOpen  && $style['nav-bar--mobile']]">
  
    <div :class="$style['nav-bar--touch']">
      <div 
        :class="[$style['nav-bar__brand-block'], isMenuOpen && $style['nav-bar__brand-block--mobile']]">
        <InlineSvg :class="[$style['nav-bar__brand-block__logo'], isMenuOpen && $style['nav-bar__brand-block__logo--active']]" alt="Company logo" src="/images/logo.svg"></InlineSvg>
        <span :class="[$style['nav-bar__brand-block__title'], isMenuOpen && $style['nav-bar__brand-block__title--mobile']]">Golden<br />Wood</span>
      </div>
      <input v-if="isMobile" type="checkbox" name="burger" id="burger" :class="$style['nav-bar__checkbox']">
      <label v-if="isMobile" for="burger" :class="$style['nav-bar__burger']" @click="toggleMenu">
        <div :class="$style['nav-bar__burger__icon']">
          <div :class="[$style['nav-bar__burger__icon__line'], isMenuOpen && $style['nav-bar__burger__icon__line--active']]"></div>
          <div :class="[$style['nav-bar__burger__icon__line'], isMenuOpen && $style['nav-bar__burger__icon__line--active']]"></div>
        </div>
      </label>
    </div>

      <div :class="[$style['nav-bar__menu'], isMenuOpen && $style['nav-bar__menu--mobile']]">
      <nav :class="[$style['nav-bar__menu__sections-list'], isMenuOpen && $style['nav-bar__menu__sections-list--mobile']]">
        <TransitionGroup appear @before-enter="onBeforeEnter" @enter="onEnter">
          <button
            v-if="isMenuOpen || !isMobile"
            :class="[$style['nav-bar__menu__sections-list__title'], (isMenuOpen) && $style['nav-bar__menu__sections-list__title--mobile']]"
            v-for="(section, index) in NAV_SECTIONS"
            :data-index="index">
            <span>{{ section.name }}</span>
          </button>
        </TransitionGroup>
      </nav>
      <PrimaryButton :class="[$style['nav-bar__menu__contact'], isMenuOpen && $style['nav-bar__menu__contact--mobile']]">
        <span>Связаться</span>
      </PrimaryButton>
    </div>

  </div>
</template>

<script setup>
import { NAV_SECTIONS } from '@/constants/services';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
import InlineSvg from 'vue-inline-svg';
import { onMounted, ref } from 'vue';
import gsap from 'gsap';

const isMobile = ref(window.innerWidth < 1025);

onMounted(() => {
  window.addEventListener('resize', () => {
    isMobile.value = window.innerWidth < 1025;
    console.log(isMobile.value);
  })
});

const isMenuOpen = ref(false);

const toggleMenu = () => isMobile && (isMenuOpen.value = !isMenuOpen.value);

const onBeforeEnter = (element) => {
  if (isMobile.value) {
    element.style.opacity = 0;
    element.style.transform = 'translateX(200px)'
  }
}

const onEnter = (element, done) => {
  if (isMobile.value) {
    gsap.to(element, {
      opacity: 1,
      x: 0,
      duration: 0.3,
      onComplete: done,
      delay: element.dataset.index * 0.12,
    })
  }
}
</script>

<style module lang="scss">
@import './NavBar.module.scss';
</style>
