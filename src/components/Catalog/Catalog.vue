<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.catalog" />
      <swiper-container 
        :slides-per-view="SERVICES_ROOMS.list.length" :space-between="8"
        @swiper="onSwiper" @swiperslidechange="onSlideChange" ref="swiper"
      >
        <SwiperSlide 
          v-for="(roomCard, index) in SERVICES_ROOMS.list" :key="index" 
          :class="$style.gallery__item"
        >
          <ImageCard
            :class="[$style.gallery__item, isActive && $style.active ]"
            :style="{ width: index === activeIndex ? '50vw' : '8vw' }"
            :image-path="roomCard.path"
          >
            <div :class="$style.gallery__item__block" v-show="index === activeIndex">
              <div :class="$style.gallery__item__block__info">
                <h3 :class="$style.gallery__item__block__info__title">{{ roomCard.name }}</h3>
                <p :class="$style.gallery__item__block__info__details">{{ roomCard.details }}</p>
              </div>
              <SecondaryButton :iconPath="'/src/assets/icon_arrow.svg'" />
            </div>
        </ImageCard>
        </SwiperSlide>
      </swiper-container>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders';
import { SERVICES_ROOMS } from '@/constants/services';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import SecondaryButton from '@/ui-kit/SecondaryButton/SecondaryButton.vue';
import { ref, computed } from 'vue';
import { register } from 'swiper/element/bundle';
import 'swiper/css';
import Swiper from 'swiper';

register();

const activeIndex = ref(0);
// const swiper = new Swiper(swiper)

// const isActive = computed((swiper) => activeIndex.value === swiper.activeIndex)

const onSwiper = (swiper) => {
  console.log(swiper);
};
const onSlideChange = (e) => {
  console.log(e);
  console.log('slide change');
  console.log(swiper);
  activeIndex.value = swiper.activeIndex
};

</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
