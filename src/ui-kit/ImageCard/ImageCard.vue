<template>
  <div :class="$style['image-card']" :style="{ backgroundImage: 'url(' + imagePath + ')' }">
    <slot></slot>
    <div :class="$style.gradient"></div>
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
