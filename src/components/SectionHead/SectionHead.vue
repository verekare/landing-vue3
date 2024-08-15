<template>
  <div :class="$style.header">
    <h2 :class="[ isLarge ? $style.header__title__large : $style.header__title ]">{{ content.title }}</h2>
    <div :class="$style.header__description">
      <span
        v-for="text in content.description"
        :class="[text.isEmphasized ? $style.header__description__emphasized : '']"
        >{{ text.content }}</span
      >
    </div>
  </div>
</template>

<script setup>
defineProps({
  content: Object,
  isLarge: Boolean
});
</script>

<style module lang="scss">
@import './SectionHead.module.scss';
</style>
