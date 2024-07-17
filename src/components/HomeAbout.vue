<template>
    <Observer 
    :observerOptions="observerOptions"
    @is-in-view="isShowFadeIn=true"
    >
    <div class="home-about">
        <h2>About us</h2>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
        <div class="about-main-content">
            <TransitionFadeIn :isShow="isShowFadeIn" class="columns">
            <div class="col fade-in">
                <h3>Lorem, ipsum.</h3>
                <p>
                    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vitae
                    maiores fuga eos provident voluptas perferendis.
                </p>
            </div>
        </TransitionFadeIn>          
        <TransitionFadeIn :isShow="isShowFadeIn" class="columns">
            <div class="col fade-in">
                <h3>Lorem, ipsum.</h3>
                <p>
                    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vitae
                    maiores fuga eos provident voluptas perferendis.
                </p>
            </div>
        </TransitionFadeIn>   
        <TransitionFadeIn :isShow="isShowFadeIn" class="columns">
            <div class="col fade-in">
                <h3>Lorem, ipsum.</h3>
                <p>
                    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vitae
                    maiores fuga eos provident voluptas perferendis.
                </p>
            </div>
        </TransitionFadeIn>   
        </div>    
    </div>
 </Observer>

</template>
<script setup>
import TransitionFadeIn from '../components/TransitionFadeIn.vue';
import Observer from './Observer.vue';
import {ref} from 'vue'
const observerOptions = {
    root: null,
    threshold: 0.9,
    rootMargin: '-50px 0px 0px 0px'
}
const isShowFadeIn = ref(false)

</script>
<style scoped>
.home-about {
  padding: 3% 6%;
  background: #f4f4f4; 
  color: #333;
}
.about-main-content {
  display: flex;
  margin-top: 25px;
}
h2,h3 {
  font-weight: 700;
}
.home-about {
  background-color: white;
  color: black;
  display: flex;
  flex-direction: column;
  padding-top: 100px;
}
.about-content {
  display: flex;
}

</style>

