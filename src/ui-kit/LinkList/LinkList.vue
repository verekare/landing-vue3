<template>
  <div :class="$style['list-block']">
    <p :class="$style['list-block__title']">{{ services.type }}</p>
    <ul :class="$style['list-block__list']">
      <Link
        :link="services.list"
        :class="$style['list-block__list__item']"
        v-for="item in services.list"
        :hasDefaultArrow="hasDefaultArrow"
      >
        {{ item.name }}</Link
      >
    </ul>
  </div>
</template>

<script setup>
import Link from '@/ui-kit/Link/Link.vue';
defineProps({
  services: Object,
  hasDefaultArrow: Boolean,
});
</script>
<style module lang="scss">
@import './LinkList.module.scss';
</style>
