<template>
  <div class="container">
    <div class="section__row">
      <SectionHead :content="content.faq" :isLarge="true" />

      <div :class="$style.faqs">
        <div v-for="(faq, index) in FAQS" key="index">
          <div :class="$style.faqs__faq">
            <div :class="$style.faqs__faq__header" @click="() => handleClick(index)">
              <div :class="$style.faqs__faq__header__marker">
                <Icon
                  :iconPath="openedStates[index] ? ICONS_PATHS.minus : ICONS_PATHS.plus"
                  :class="[openedStates[index] && style.icon__active]"
                />
              </div>
              <h3
                :class="[style.faqs__faq__header__question, openedStates[index] && style.faqs__faq__header__question__opened]"
              >
                {{ faq.question }}
              </h3>
            </div>
            <div :class="[style.faqs__faq__answer, openedStates[index] && style.faqs__faq__answer__opened]">
              <p>{{ faq.answer }}</p>
            </div>
          </div>
          <span v-if="index != FAQS.length" :class="$style.divider"></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useCssModule, ref, computed, normalizeClass } from 'vue';
import content from '@/constants/sectionHeaders';
import { FAQS } from '@/constants/services';
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import Icon from '@/ui-kit/Icon/Icon.vue';
import { ICONS_PATHS } from '@/constants/icons';

let openedStates = ref(FAQS.map(() => false));
const handleClick = (index) => {
  openedStates.value[index] = !openedStates.value[index];
};

const style = useCssModule();
</script>
<style module lang="scss">
@import './Faq.module.scss';
</style>
