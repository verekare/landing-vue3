<template>
  <div class="sectionLayout">
    <SectionHead :content="content.services" />
    <div :class="$style.serviceCards">
      <ImageCard
        v-for="service in SERVICES"
        :class="$style.singleCard"
        :image-path="service.path"
      >
        <h4 :class="$style.cardName">{{ service.name }}</h4>
        <SmallButton
          :class="$style.smallButton"
          :iconPath="'/src/assets/arrow.svg'"
        ></SmallButton>
      </ImageCard>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import content from '@/constants/sectionHeaders.js';
import { SERVICES } from '@/constants/services';
import SmallButton from '@/ui-kit/SmallButton/SmallButton.vue';
</script>

<style module lang="scss">
@import './Services.module.scss';
</style>
