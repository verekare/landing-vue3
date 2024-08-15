<template>
  <div :class="$style['contact-block']">
    <SectionHead :content="content.contact" :class="$style['contact-block__header']" />
    <PrimaryButton :isLarge="true">Связаться</PrimaryButton>
  </div>

  <div :class="$style['footer']">
    <div :class="$style.footer__main">
      <div :class="$style['footer__main__info']">
        <h2 :class="$style['footer__main__info__title']">{{ content.footer.title }}</h2>
        <div :class="$style['footer__main__info__description']">
          <span
            v-for="text in content.footer.description"
            :class="[text.isEmphasized ? $style.footer__info__description__emphasized : '']"
            >{{ text.content }}</span
          >
        </div>
        <a :href="'mailto:' + content.footer.path" class="anchorLink">
          {{ content.footer.link }}
        </a>
      </div>
      <div :class="$style.footer__main__nav">
        <LinkList :hasDefaultArrow="false" :services="SERVICES_ROOMS"></LinkList>
        <LinkList :hasDefaultArrow="false" :services="SERVICES_FURNITURE"></LinkList>
      </div>
    </div>
    <span :class="$style.divider"></span>
    <div :class="$style['footer__bottom']">
      <span :class="$style['footer__bottom__copyright']">{{ content.footer.copyright }}</span>
      <ul :class="$style['footer__bottom__social-links']">
        <Link
          v-for="item in content.footer.contacts"
          :class="$style['footer__bottom__social-links__item']"
          :link="content.footer.contacts"
          :hasDefaultArrow="true"
          >{{ item.name }}</Link
        >
      </ul>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders';
import PrimaryButton from '@/ui-kit/PrimaryButton/PrimaryButton.vue';
import LinkList from '@/ui-kit/LinkList/LinkList.vue';
import Link from '@/ui-kit/Link/Link.vue';
import { SERVICES_FURNITURE, SERVICES_ROOMS } from '@/constants/services';
</script>

<style module lang="scss">
@import './Footer.module.scss';
</style>
