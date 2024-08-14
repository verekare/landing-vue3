<template>
  <div class="container">
    <div class="rowLayout">
      <SectionHead :content="content.faq" :class="$style.sectionHead" />

      <div :class="$style.faqsAccordion">
        <div v-for="(faq, index) in FAQS" key="index">
          <div :class="$style.faqElement">
            <div :class="$style.faqHeader" @click="() => handleClick(index)">
              <div :class="$style.faqMarker">
                <Icon
                  :iconPath="openedStates[index] ? ICONS_PATHS.minus : ICONS_PATHS.plus"
                  :class="[openedStates[index] && style.activeIcon]"
                />
              </div>
              <h3
                :class="[style.faqQuestion, openedStates[index] && style.openedQuestion]"
              >
                {{ faq.question }}
              </h3>
            </div>
            <div :class="[style.faqAnswer, openedStates[index] && style.openedAnswer]">
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
  console.log(openedStates);
};

const style = useCssModule();

const faqQuestionClassName = (index) => {
  return normalizeClass([
    style.faqQuestion,
    openedStates.value[index] && style.openedQuestion,
  ]);
};

// const faqAnswerClassName = (index) => {
//   return normalizeClass([
//     style.faqAnswer,
//     openedStates.value[index] && style.openedAnswer,
//   ]);
// };
</script>
<style module lang="scss">
@import './Faq.module.scss';
</style>
