<template>
  <button :class="$style.button__small">
    <Icon :isBig="true" :iconPath="iconPath" />
  </button>
</template>
<script setup>
import Icon from '@/ui-kit/Icon/Icon.vue';
defineProps({
  iconPath: {
    type: String,
    required: true,
  }
});
</script>

<style module lang="scss">
@import './SecondaryButton.module.scss';
</style>
