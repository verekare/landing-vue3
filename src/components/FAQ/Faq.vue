<template>
  <div class="rowLayout">
    <div :class="$style.faqLayout">
      <h2 :class="$style.contactTitle">{{ content.faq.title }}</h2>
      <div :class="$style.contactDesctiption">
        <span>{{ content.faq.description }}</span>
        <span :class="$style.emphasizedText">{{ content.faq.emphasized }}</span>
      </div>
    </div>
    <div :class="$style.accordionBlock">
      <div v-for="question in FAQ_CONTENT">
        <details>
          <summary :class="$style.faqQuestion">{{ question.question }}</summary>
          <p :class="$style.faqAnswer">{{ question.answer }}<</p>
        </details>
        <span :class="$style.divider"></span>
      </div>
    </div>
  </div>
</template>

<script setup>
import content from '@/constants/sectionHeaders';
import { FAQ_CONTENT } from '@/constants/services';
</script>
<style module lang="scss">
@import './Faq.module.scss';
</style>
