<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.catalog" />
      <Swiper 
        :slides-per-view="SERVICES_ROOMS.list.length" :space-between="8"
        @swiper="onSwiper" @slideChange="onSlideChange"
      >
        <SwiperSlide 
          v-for="(roomCard, index) in SERVICES_ROOMS.list" :key="index" 
          :class="$style.gallery__item"
          :style="{ width: index === activeIndex ? '50vw' : '8vw' }"
        >
          <ImageCard
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
        </SwiperSlide>
      </Swiper>
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
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
// import { Autoplay } from 'swiper/modules';

// const modules = [Autoplay];
const activeIndex = ref(0);

const onSwiper = (swiper) => {
  console.log(swiper);
};
const onSlideChange = (swiper) => {
  console.log('slide change');
  console.log(swiper);
  activeIndex.value = swiper.activeIndex
};

</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
