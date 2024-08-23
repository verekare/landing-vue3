<template>
  <div 
    :style="{ backgroundImage: `linear-gradient(90deg, rgb(0 0 0 / 0.3) 44%, rgb(0 0 0 / 0) 100%), url(${HERO_IMAGE_PATH.path})` }"
    :class="$style['hero-block']" 
  >
    <NavBar />
    <div :class="$style['hero-block__content']">
      <h1 :class="$style['hero-block__content__title']">Мебель на заказ</h1>
      <p :class="$style['hero-block__content__description']">
        Производим мебель в Нижнем Новгороде<br />по индивидуальным размерам
      </p>
      <PrimaryButton :class="$style['hero-block__button']">Рассчитать стоимость</PrimaryButton>
    </div>
  </div>
</template>

<script setup>
// import { AdvancedImage } from '@cloudinary/vue';
// import { Cloudinary } from '@cloudinary/url-gen';
import NavBar from '@/components/NavBar/NavBar.vue';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
import { HERO_IMAGE_PATH } from '@/constants/services';

// const cld = new Cloudinary({
//   cloud: {
//     cloudName: 'depmjjxzk',
//     uploadPreset: 'depmjjxzk_preset'
//   }
// })

// const urlImage = cld.image('golden-wood_images/hero-block');
</script>

<style module lang="scss">
@import './HeroBlock.module.scss';
</style>
