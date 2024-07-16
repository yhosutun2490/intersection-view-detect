
<template>
  <div class="container">
    <Header class="header-wrapper" :class="[headerWhite? 'header-scroll' : '']"></Header>
    <Observer 
    @is-in-view="headerWhite=false"
    @is-outside-view="headerWhite=true"
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
import Observer from './components/Observer.vue'
import {ref} from 'vue'
const headerWhite = ref(false)
const homeIntroOptions = {
  rootMargin: '-50px 0px 0px 0px'
}

</script>
<style scoped>
.container {
  max-width: 100dvw;
  height: 100dvh;

}
.header-wrapper {
  position: fixed;
  width: 100%;
}
.header-wrapper.header-scroll {
  background-color: white;
  color: black;
  box-shadow: 1px 1px 5px rgba(0,0,0,0.5);
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
