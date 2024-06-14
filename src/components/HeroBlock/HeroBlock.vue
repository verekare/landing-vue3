<template>
  <div :class="$style.heroImage">
    <PageHeader />
    <h1 :class="$style.title">Мебель на заказ</h1>
    <p :class="$style.description">
      Производим мебель в Нижнем Новгороде<br />по индивидуальным размерам
    </p>
    <PrimaryButton :class="$style.heroButton">Рассчитать стоимость</PrimaryButton>
  </div>
</template>

<script setup>
import PageHeader from '../PageHeader/PageHeader.vue';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
</script>

<style module lang="scss">
@import './HeroBlock.module.scss';
</style>
