<template>
  <button :class="isLarge ? $style.button__large : $style.button__default">
    <slot></slot>
  </button>
</template>

<script setup>
defineProps({
  isLarge: Boolean,
});
</script>
<style module lang="scss">
@import './PrimaryButton.module.scss';
</style>
