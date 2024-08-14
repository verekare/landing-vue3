<template>
  <div class="container">
    <div class="sectionLayout">
      <SectionHead :content="content.catalog" />
      <div :class="$style.roomsGallery" ref="slider">
        <ImageCard
          v-for="(room, index) in SERVICES_ROOMS.list"
          :key="index"
          :data-index="index"
          :class="$style.singleCard"
          :image-path="room.path"
        >
          <div :class="$style.cardDetailsWrapper">
            <div :class="$style.textWrapper">
              <h3 :class="$style.cardName">{{ room.name }}</h3>
              <p :class="$style.cardDetails">{{ room.details }}</p>
            </div>
            <SmallButton :iconPath="'/src/assets/icon_arrow.svg'" />
          </div>
        </ImageCard>
      </div>
    </div>
  </div>
</template>

<script setup>
import SectionHead from '@/components/SectionHead/SectionHead.vue';
import content from '@/constants/sectionHeaders';
import { SERVICES_ROOMS } from '@/constants/services';
import ImageCard from '@/ui-kit/ImageCard/ImageCard.vue';
import SmallButton from '@/ui-kit/SmallButton/SmallButton.vue';
import { ref, onMounted } from 'vue';
import gsap from 'gsap';

const slider = ref(null);
const timeline = gsap.timeline();
onMounted(() => {
  const imageGallery = slider.value.children;
  // console.log(slider.value.children);
  // for (let i = 0; i < imageGallery.length; i++) {
  //   let imageCard = imageGallery[i];
  //   console.log(imageCard);
  //   timeline.to(imageCard, {
  //     width: 650,
  //     duration: 2,
  //     delay: i * 4,
  //   })
  //   .to(imageCard, {
  //     width: 165,
  //     duration: 2,
  //   })
  // }
})

const cardsTimeline = [];

const onEnter = (element, done) => {
  const delay = element.dataset.index;
  // timeline.set(element, { width: 165 });

  // console.log('on Enter', timeline, delay);
  // });

  // cardsTimeline.push(timeline);
  // console.log('cards Timeline has', cardsTimeline);
};

const onAfterEnter = (element, done) => {
  const timeline = gsap.timeline({
    onComplete: done,
    defaults: {
      duration: 2,
      // repeat: 3,
      // repeatDelay: 24,
    },
  });

  const delay = element.dataset.index;
  // const timeline = cardsTimeline[delay];
  console.log('on After Enter', delay);
  console.log(timeline);
  // const setOpened = gsap.set(element, { width: 650, delay: delay * 4 });
  if (timeline) {
    timeline
      .to(element, { width: 650, delay: delay * 4, duration: 2 })
      .to({}, 2, {})
      .to(element, { width: 165, delay: delay * 4, duration: 2 });
    // .to(
    //   element.nextElementSibling,
    //   { width: 165, delay: delay * 4, duration: 2 },
    //   '-=1'
    // );
  }
  console.log('on After Enter: Element number', delay);
};

// const onAfterLeave = (element) => { }
</script>

<style module lang="scss">
@import './Catalog.module.scss';
</style>
