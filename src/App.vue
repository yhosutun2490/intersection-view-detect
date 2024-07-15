
<template>
  <div class="container">
    <Header class="header-wrapper" :class="[headerOutOfView? 'sticky' : '']"></Header>
    <Observer 
    @is-in-view="headerOutOfView=false"
    @is-outside-view="headerOutOfView=true"
    :observerOptions="homeIntroOptions"
    >
      <HomeIntro></HomeIntro>
    </Observer>
    <HomeAbout></HomeAbout>
    <HomeMoreStuff></HomeMoreStuff>
  </div>
</template>
<script setup>
import Header from './components/Header.vue';
import HomeAbout from './components/HomeAbout.vue';
import HomeIntro from './components/HomeIntro.vue';
import HomeMoreStuff from './components/HomeMoreStuff.vue'
import {ref} from 'vue'
const headerOutOfView = ref(false)
const homeIntroOptions = {
  threshold: 1,
  rootMargin: '-200px 0px 0px 0px'
}

</script>
<style scoped>
.container {
  width: 100dvw;
  height: 100dvh;

}
.header-wrapper {
  position: fixed;
}
.header-wrapper.sticky {
  background-color: white;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
