<template>
  <button @click="window.open(link.path)" type="submit" :class="$style.link">
    <slot></slot>
    <InlineSvg :class="$style.iconArrow" src="@/assets/arrow.svg"></InlineSvg>
  </button>
</template>

<script setup>
import InlineSvg from 'vue-inline-svg';
defineProps({
  link: {
    name: String,
    path: String,
  },
});
</script>

<style module lang="scss">
@import './Link.module.scss';
</style>
