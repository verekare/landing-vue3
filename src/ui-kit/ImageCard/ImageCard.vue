<template>
  <div :class="$style.imageCard" :style="{ backgroundImage: 'url(' + imagePath + ')' }">
    <div :class="$style.cardContent">
      <slot></slot>
    </div>
    <div :class="$style.gradientLayer"></div>
  </div>
</template>

<script setup>
const props = defineProps({
  imagePath: String,
});
</script>
<style module lang="scss">
@import './ImageCard.module.scss';
</style>
