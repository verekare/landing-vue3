<template>
  <span :class="[isBig ? $style['icon-block--big'] : $style['icon-block']]">
    <InlineSvg :src="iconPath"></InlineSvg>
  </span>
</template>

<script setup>
import InlineSvg from 'vue-inline-svg';

defineProps({
  iconPath: {
    type: String,
    required: true,
  },
  isBig: {
    type: Boolean,
    required: false,
  }
});
</script>

<style module lang="scss">
@import './Icon.module.scss';
</style>
