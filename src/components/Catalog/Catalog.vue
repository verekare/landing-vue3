<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.catalog" />

      <div :class="$style.gallery">
        <ImageCard
          v-for="(roomCard, index) in SERVICES_ROOMS.list" :key="index" 
          :class="[$style.gallery__item, (index === activeIndex) && $style['gallery__item--active'] ]"
          :image-path="roomCard.path"
          :isActive="(index === activeIndex)"
        >
            <div :class="$style.gallery__item__block">
              <div :class="$style.gallery__item__block__info">
                <h3 :class="$style.gallery__item__block__info__title">{{ roomCard.name }}</h3>
                <p :class="$style.gallery__item__block__info__details">{{ roomCard.details }}</p>
              </div>
              <SecondaryButton :iconPath="ICONS_PATHS.arrow" />
            </div>
      </ImageCard>
      </div>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders';
import { SERVICES_ROOMS } from '@/constants/services';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import SecondaryButton from '@/ui-kit/SecondaryButton/SecondaryButton.vue';
import { ICONS_PATHS } from '@/constants/icons';
import { ref, onMounted, onUnmounted } from 'vue';

const activeIndex = ref(0);
const intervalId = ref(null);

onMounted(() => {
  intervalId.value = setInterval(() => {
    if (activeIndex.value < SERVICES_ROOMS.list.length - 1) {
      activeIndex.value++;
    } else {
      activeIndex.value = 0
    }
  }, 4000)
})

onUnmounted(() => {
  clearInterval(intervalId.value)
})

</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
