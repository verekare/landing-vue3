<template>
  <div 
    :style="{ backgroundImage: `linear-gradient(90deg, rgb(0 0 0 / 0.3) 44%, rgb(0 0 0 / 0) 100%), url(${heroImage})` }"
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

// const cld = new Cloudinary({
//   cloud: {
//     cloudName: 'depmjjxzk',
//     uploadPreset: 'depmjjxzk_preset'
//   }
// })

// const urlImage = cld.image('golden-wood_images/hero-block');
const heroImage = 'https://res.cloudinary.com/depmjjxzk/image/upload/v1724420039/golden-wood_images/hero-block.jpg';
</script>

<style module lang="scss">
@import './HeroBlock.module.scss';
</style>
