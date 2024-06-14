<template>
  <div :class="$style.headerPanel">
    <div :class="$style.companyMark">
      <img alt="Company logo" src="@/assets/logo.svg" />
      <span :class="$style.companyName">Golden<br />Wood</span>
    </div>
    <nav :class="$style.navPanel">
      <button :class="$style.sectionName" v-for="section in NAV_SECTIONS">
        <span>{{ section.name }}</span>
      </button>
    </nav>
    <PrimaryButton :class="$style.contactLink">
      <span>Связаться</span>
    </PrimaryButton>
  </div>
</template>

<script setup>
import { NAV_SECTIONS } from '@/constants/services';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
</script>

<style module lang="scss">
@import './PageHeader.module.scss';
</style>
