<template>
  <div :class="$style['image-card']" :style="{ backgroundImage: 'url(' + imagePath + ')' }">
      <slot></slot>
    <div :class="$style['image-card__gradient']" v-show="props.isActive"></div>
  </div>
</template>

<script setup>
const props = defineProps({
  imagePath: String,
  isActive: Boolean
});
</script>
<style module lang="scss">
@import './ImageCard.module.scss';
</style>
