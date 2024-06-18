<template>
  <div :class="$style.sectionHead">
    <h2 :class="$style.sectionTitle">{{ content.title }}</h2>
    <div :class="$style.sectionDesctiption">
      <span>{{ content.description }}</span>
      <span :class="$style.emphasizedText">{{ content.emphasized }}</span>
      <span :class="$style.description">{{ content.ending }}</span>
    </div>
  </div>
</template>

<script setup>
defineProps({
  content: Object,
});
</script>

<style module lang="scss">
@import './SectionHead.module.scss';
</style>
