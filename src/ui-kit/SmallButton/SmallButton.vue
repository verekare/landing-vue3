<template>
  <button :class="$style.button__small">
    <span :class="$style['icon-block']">
      <InlineSvg :src="iconPath"></InlineSvg>
    </span>
  </button>
</template>
<script setup>
import InlineSvg from 'vue-inline-svg';
defineProps({
  iconPath: String,
});
</script>

<style module lang="scss">
@import './SmallButton.module.scss';
</style>
