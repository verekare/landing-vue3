<template>
  <div :class="$style['nav-bar']">
    <div :class="$style['nav-bar__brand-block']">
      <img :class="$style['nav-bar__brand-block__logo']" alt="Company logo" src="@/assets/logo.svg" />
      <span :class="$style['nav-bar__brand-block__title']">Golden<br />Wood</span>
    </div>
    <nav :class="$style['nav-bar__sections-list']">
      <button :class="$style['nav-bar__sections-list__title']" v-for="section in NAV_SECTIONS">
        <span>{{ section.name }}</span>
      </button>
    </nav>
    <PrimaryButton :class="$style['nav-bar__contact']">
      <span>Связаться</span>
    </PrimaryButton>
  </div>
</template>

<script setup>
import { NAV_SECTIONS } from '@/constants/services';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
</script>

<style module lang="scss">
@import './NavBar.module.scss';
</style>
