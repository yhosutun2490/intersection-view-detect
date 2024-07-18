<template>
  <div class="home-more-stuff">
    <div class="more-stuff-grid" v-for="(item, key) in slideFadeInStates" :key="key">
      <Observer 
      class="more-stuff-grid-observer"
      @is-in-view="handleSlideInSignal(key,true)"
      @is-outside-view="handleSlideInSignal(key,false)"
      :observerOptions="slideObserveOptions"
      >
        <img src="https://unsplash.it/400" alt="" class="slide-in"
          :class="[key % 2 ? 'from-left' : 'from-right', item.isInView ? 'appear' : '']" />
        <p class="slide-in" :class="[key % 2 ? 'from-right' : 'from-left', , item.isInView ? 'appear' : '']">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
          magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
          reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
          facilis quibusdam magni. Eveniet.
        </p>
      </Observer>
    </div>
  </div>
</template>
<script setup>

import {ref} from "vue"
import Observer from '../components/Observer.vue'
// v-for multiple slide in signals should be array 
const slideFadeInStates = ref({
  1: {
    isInView: false
  },
  2: {
    isInView: false
  },
  3: {
    isInView: false
  },
  4: {
    isInView: false
  },
}) 
const slideObserveOptions = {
  root: null,
  threshold: 0,
  rootMargin: '0px 0px -250px 0px'
}
function  handleSlideInSignal(key,signal) {
  slideFadeInStates.value[key].isInView = signal
}

</script>

<style scoped>
.home-more-stuff {
  width: 100%;
}

.more-stuff-grid-observer {
  background: #f4f4f4;
  padding: 4em 0;
  display: grid;
  grid-gap: 2em;
  align-items: center;
  grid-template-columns: minmax(1em, 1fr) repeat(2, minmax(200px, 400px)) minmax(
      1em,
      1fr
    );
}

.from-left {
  grid-column: 2 / 3;
  grid-row: 1;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.from-right {
  grid-column: 3 / 4;
  grid-row: 1;
  -webkit-transform: translateX(50%);
  transform: translateX(50%);
}
.from-left,.from-right {
 transition: opacity 250ms ease-in ,transform 400ms ease-in;
 opacity: 0;
}

.from-left.appear,.from-right.appear {
 opacity: 1;
 -webkit-transform: translateX(0);
  transform: translateX(0);
}
p {
  color: #333;
}

</style>
