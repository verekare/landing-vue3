<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.services" />
      <div :class="$style.services__list">
        <ImageCard
          v-for="service in SERVICES"
          :class="$style.services__item"
          :image-path="service.path"
        >
          <h4 :class="$style.services__itemitle">{{ service.name }}</h4>
          <SmallButton
            :class="$style.button__small"
            :iconPath="'/src/assets/icon_arrow.svg'"
          ></SmallButton>
        </ImageCard>
      </div>
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
