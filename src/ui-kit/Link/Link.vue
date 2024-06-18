<template>
  <button @click="window.open(link.path)" type="submit" :class="$style.link">
    <slot></slot>
    <span :class="hasDefaultArrow ? $style.iconArrow : $style.iconArrowHidden">
      <InlineSvg src="/src/assets/arrow.svg"></InlineSvg>
    </span>
  </button>
</template>

<script setup>
import InlineSvg from 'vue-inline-svg';
defineProps({
  link: {
    name: String,
    path: String,
  },
  hasDefaultArrow: Boolean,
});
</script>

<style module lang="scss">
@import './Link.module.scss';
</style>
