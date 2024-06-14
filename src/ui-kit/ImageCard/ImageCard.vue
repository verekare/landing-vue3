<template>
  <div :class="$style.imageCard" :style="{ backgroundImage: 'url(' + imagePath + ')' }">
    <slot></slot>
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
