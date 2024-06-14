<template>
  <div class="sectionLayout">
    <SectionHead :content="content.catalog" />
    <div :class="$style.roomsGallery">
      <ImageCard
        v-for="room in SERVICES_ROOMS.list"
        :class="$style.singleCard"
        :image-path="room.path"
      >
        <div :class="$style.cardDetailsWrapper">
          <div :class="$style.textWrapper">
            <h3 :class="$style.cardName">{{ room.name }}</h3>
            <p :class="$style.cardDetails">{{ room.details }}</p>
          </div>
          <SmallButton :iconPath="'/src/assets/arrow.svg'" />
        </div>
      </ImageCard>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders';
import { SERVICES_ROOMS } from '@/constants/services';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import SmallButton from '@/ui-kit/SmallButton/SmallButton.vue';
</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
