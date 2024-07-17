<template>
  <div class="home-more-stuff">
   <div class="more-stuff-grid" v-for="number in 4" :key="number">
      <img src="https://unsplash.it/400" alt="" class="slide-in" 
      :class="[number % 2 ?'from-left':'from-right',slideFadeIn?'appear':'']"
      />
      <p class="slide-in" 
      :class="[number % 2 ?'from-right':'from-left',,slideFadeIn?'appear':'']"
      >
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis fugit, quae beatae vero sit
        magni quaerat id ratione. Dolor optio unde amet omnis sapiente neque cumque consequuntur
        reiciendis deserunt. Dolorem vero exercitationem consequuntur, eligendi cupiditate debitis
        facilis quibusdam magni. Eveniet.
      </p>
    </div>
  </div>
</template>
<script setup>

import {ref, onMounted} from "vue"
const slideFadeIn = ref(false)
// const slideObserveOptions = {
//   root: null,
//   rootMargin: '0px 0px 0px 0px'
// }
onMounted(()=>{
  setTimeout(() => {
    slideFadeIn.value = true
  }, 5000);
})
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
 transition: opacity 250ms ease-in transform 400ms ease-in;
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
