<template>
  <div>
    <button @click="toggleItems">Toggle Items</button>
    <transition-group name="list" tag="div" @enter="onEnter" @after-enter="onAfterEnter">
      <div
        v-for="(item, index) in items"
        :key="item.id"
        :data-index="index"
        class="list-item"
      >
        {{ item.name }}
      </div>
    </transition-group>
  </div>
</template>

<script>
import gsap from 'gsap';

export default {
  data() {
    return {
      items: [],
      timelines: [], // Массив для хранения временных шкал
    };
  },
  methods: {
    toggleItems() {
      // Тоггл списка
      if (this.items.length === 0) {
        this.items = [
          { id: 1, name: 'Item 1' },
          { id: 2, name: 'Item 2' },
          { id: 3, name: 'Item 3' },
        ];
      } else {
        this.items = [];
      }
    },
    onEnter(el, done) {
      gsap.set(el, { width: '33%' });

      // const index = Array.from(el.parentNode.children).indexOf(el);

      // Создаем новую временную шкалу для каждого элемента
      const timeline = gsap.timeline({
        onComplete: done,
      });

      // Добавляем анимацию с задержкой, зависящей от индекса
      timeline.to(el, { width: '100%', duration: 2, delay: el.dataset.index * 2 });

      // Сохраняем временную шкалу в массив
      this.timelines.push(timeline);
    },
    onAfterEnter(el) {
      const index = Array.from(el.parentNode.children).indexOf(el);

      // Уменьшаем ширину после завершения анимации входа с задержкой
      gsap.to(el, { width: '50%', duration: 2, delay: index * 2 });
    },
  },
};
</script>

<style>
.list {
  display: flex;
  flex-direction: row;
  gap: 20px;
}

.list-item {
  overflow: hidden;
  background-color: #e08d8d;
  margin: 5px 0;
  padding: 10px;
  width: 100px; /* Начальная ширина */
}
</style>
