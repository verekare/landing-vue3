<template>
  <div :class="$style.sectionHead">
    <h2 :class="$style.sectionTitle">{{ content.title }}</h2>
    <div :class="$style.sectionDesctiption">
      <span
        v-for="text in content.description"
        :class="text.isEmphasized ? $style.emphasizedText : $style.description"
        >{{ text.content }}</span
      >
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
