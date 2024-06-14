<template>
  <div :class="$style.contactBlock">
    <SectionHead :content="content.contact" :class="$style.contactHead" />
    <PrimaryButton :isBig="true">Связаться</PrimaryButton>
  </div>

  <div :class="$style.footerBlock">
    <div :class="$style.footerTop">
      <div :class="$style.footerHeader">
        <h2 :class="$style.footerTitle">{{ content.footer.title }}</h2>
        <div :class="$style.sectionDesctiption">
          <span>{{ content.footer.description }}</span>
          <span :class="$style.emphasizedText">{{ content.footer.emphasized }}</span>
        </div>
        <a :href="'mailto:' + content.footer.path" class="anchorLink">
          {{ content.footer.link }}
        </a>
      </div>
      <div :class="$style.linkLists">
        <LinkList :services="SERVICES_ROOMS"></LinkList>
        <LinkList :services="SERVICES_FURNITURE"></LinkList>
      </div>
    </div>
    <span :class="$style.divider"></span>
    <div :class="$style.footerBottom">
      <span :class="$style.copyright">{{ content.footer.copyright }}</span>
      <ul :class="$style.contactLinkList">
        <Link
          v-for="item in content.footer.contacts"
          :class="$style.contactLinkItem"
          :link="content.footer.contacts"
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
