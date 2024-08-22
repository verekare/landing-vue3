<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.catalog" />
        <div :class="$style.gallery" ref="slider">
          <ImageCard
            v-for="(roomCard, index) in SERVICES_ROOMS.list" :key="index" :data-index="index"
            :class="[$style.gallery__item, isActive && $style.active ]"
            :image-path="roomCard.path"
          >
            <div :class="$style.gallery__item__block">
              <div :class="$style.gallery__item__block__info">
                <h3 :class="$style.gallery__item__block__info__title">{{ roomCard.name }}</h3>
                <p :class="$style.gallery__item__block__info__details">{{ roomCard.details }}</p>
              </div>
              <SecondaryButton :iconPath="'/src/assets/icon_arrow.svg'" />
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
import { ref, onMounted, computed } from 'vue';
import gsap from 'gsap';

const slider = ref(null);

onMounted(() => {
  const timeline = gsap.timeline();
  const gallery = Array.from(slider.value.children);

  gallery.forEach((el, index) => {
    timeline.to(el, { width: 1200, delay: index * 4, duration: 2 })
            .to(el, { width: 165, delay: index * 4, duration: 2 });
    console.log(timeline);
  })
})

</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
