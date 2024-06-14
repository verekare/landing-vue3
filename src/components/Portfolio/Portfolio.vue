<template>
  <div class="sectionLayout">
    <SectionHead :content="content.portfolio" />
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders.js';
</script>

<style module lang="scss">
@import './Portfolio.module.scss';
</style>
