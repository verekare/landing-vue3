<template>
  <div class="container">
    <div class="section">
      <SectionHead :content="content.portfolio" />
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders.js';
</script>

<style module lang="scss">
@import './Portfolio.module.scss';
</style>
