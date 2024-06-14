<template>
  <button :class="isBig ? $style.bigPrimaryButton : $style.primaryButton">
    <slot></slot>
  </button>
</template>

<script setup>
defineProps({
  isBig: Boolean,
});
</script>
<style module lang="scss">
@import './PrimaryButton.module.scss';
</style>
