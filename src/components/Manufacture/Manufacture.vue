<template>
  <div class="container">
    <div class="sectionLayout">
      <SectionHead :content="content.manufacture" />
      <div :class="$style.imageGallery">
        <ImageCard
          v-for="imagePath in MANUFACTURE_IMAGE_PATHS"
          :image-path="imagePath.path"
          :class="$style.imageCard"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders.js';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import { MANUFACTURE_IMAGE_PATHS } from '@/constants/services';
</script>

<style module lang="scss">
@import './Manufacture.module.scss';
</style>
