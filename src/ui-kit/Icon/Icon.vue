<template>
  <span :class="$style['icon-block']">
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
});
</script>

<style module lang="scss">
@import './Icon.module.scss';
</style>
