
<template>
  <div class="container">
<<<<<<< HEAD
    <Header class="header-wrapper" :class="[headerOutOfView? 'nav-scroll' : '']"></Header>
=======
    <Header class="header-wrapper" :class="[headerWhite? 'header-scroll' : '']"></Header>
>>>>>>> 6c69ba6ecd9fc0f1ac6ee30999cfa586828eaf5c
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
import Observer from './components/Observer.vue';
import {ref} from 'vue'
const headerWhite = ref(false)
const homeIntroOptions = {
  threshold: 0,
  rootMargin: '-200px 0px 0px 0px'
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
<<<<<<< HEAD
.header-wrapper.nav-scroll {
  color: #333;
  background: #f4f4f4;
  box-shadow: 0 3px 20px rgba(0, 0, 0, 0.2);
=======
.header-wrapper.header-scroll {
  background-color: white;
  color: black;
  box-shadow: 1px 1px 5px rgba(0,0,0,0.5);
>>>>>>> 6c69ba6ecd9fc0f1ac6ee30999cfa586828eaf5c
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
