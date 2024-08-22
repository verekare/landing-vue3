<template>
<div class="container">
  <swiper 
    :loop="true" 
    :slides-per-view="4" 
    :space-between="8" 
    slideActiveClass="swiper-slide-active"
    centered-slides="true" 
    @swiper="onSwiper"
    class="swiper"
  >
    <div class="swiper-wrapper">
      <swiper-slide> <div class="box one">img 1</div> </swiper-slide>
      <swiper-slide> <div class="box two">vid 1</div> </swiper-slide>
      <swiper-slide> <div class="box three">img 2</div> </swiper-slide>
      <swiper-slide> <div class="box four">img 3</div> </swiper-slide>
    </div>
  </swiper>
</div>
</template>

<script setup>
import { register } from 'swiper/element/bundle';
import 'swiper/css';
register();

const onSwiper = (swiper) => {
  window.swiper = swiper;
}
</script>

<style lang="scss" scoped>
.container {
  padding: 7.5em 2.5em;
  max-width: 1200px;
  display: flex;
  flex-direction: row;
}

.swiper {
  position: relative;
}

.swiper-wrapper {
  display: flex;
  flex-direction: row;
}

.swiper-slide {
  flex-shrink: 0;
  flex-basis: 0;
  width: 10vw;
  transition: flex-basis 0.8s cubic-bezier(0.22, 1, 0.36, 1), width 0.8s cubic-bezier(0.22, 1, 0.36, 1);
}

.swiper-slide.swiper-slide-active{
  flex-basis: 50%;
  width: auto;
}

.box {
  position: relative;
  height: 40vh;
}

.one {
  background-color: tomato;
}

.two {
  background-color: turquoise;
}

.three {
  background-color: palevioletred;
}

.four {
  background-color: royalblue;
}
</style>