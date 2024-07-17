<template>
  <div class="home-more-stuff">
    <Observer  
    @is-in-view="slideFadeIn=true"
    @is-outside-view="slideFadeIn=false"
    :observerOptions="slideObserveOptions"
    >
      <div class="more-stuff-grid">
      <img src="https://unsplash.it/400" alt="" class="slide-in from-left" :class="[slideFadeIn?'appear': '']"/>
      <p class="slide-in from-right" :class="[slideFadeIn?'appear': '']">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
    </div>
    </Observer>
  
    <!-- <div class="more-stuff-grid">
      <p class="slide-in from-left">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
      <img src="https://unsplash.it/401" alt="" class="slide-in from-right" />
    </div>
    <div class="more-stuff-grid">
      <img src="//unsplash.it/400" alt="" class="slide-in from-left" />
      <p class="slide-in from-right">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
    </div>
    <div class="more-stuff-grid">
      <p class="slide-in from-left">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
      <img src="https://unsplash.it/401" alt="" class="slide-in from-right" />
    </div>
    <div class="more-stuff-grid">
      <img src="//unsplash.it/400" alt="" class="slide-in from-left" />
      <p class="slide-in from-right">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
    </div>
    <div class="more-stuff-grid">
      <p class="slide-in from-left">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
      <img src="https://unsplash.it/401" alt="" class="slide-in from-right" />
    </div> -->
  </div>
</template>
<script setup>
import Observer from "../components/Observer.vue"
import {ref} from "vue"
const slideFadeIn = ref(false)
const slideObserveOptions = {
  threshold: 1,
  rootMargin: '0px 0px -100px 0px'
}
</script>

<style scoped>
.home-more-stuff {
  width: 100%;
}

.more-stuff-grid {
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
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
}

.from-right {
  grid-column: 3 / 4;
  -webkit-transform: translateX(50%);
  transform: translateX(50%);
}
.from-left,.from-right {
 transition: opacity 250ms ease transform 400ms ease;
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
