<template>
  <div :class="$style.list">
    <p :class="$style.listTitle">{{ services.type }}</p>
    <ul :class="$style.linkList">
      <Link
        :link="services.list"
        :class="$style.listItem"
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
