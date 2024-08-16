<template>
  <div :class="$style['hero-block']">
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
import NavBar from '@/components/NavBar/NavBar.vue';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
</script>

<style module lang="scss">
@import './HeroBlock.module.scss';
</style>
