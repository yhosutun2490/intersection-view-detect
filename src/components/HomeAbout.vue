<template>
    <Observer 
    :observerOptions="observerOptions"
    @is-in-view="isShowFadeIn=true"
    >
        <div class="home-about">
        <h2>About us</h2>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
        <TransitionFadeIn :isShow="isShowFadeIn" class="columns">
                <div class="col fade-in">
                    <h3>Lorem, ipsum.</h3>
                    <p>
                     Lorem ipsum dolor sit, amet consectetur adipisicing elit. Vitae
                     maiores fuga eos provident voluptas perferendis.
                    </p>
                </div>
                <div class="col fade-in">
                <h3>A, illo!</h3>
                <p>
                    Lorem, ipsum dolor sit amet consectetur adipisicing elit.
                    Voluptatibus minima quo beatae eius blanditiis officiis.
                </p>
            </div>
            <div class="col fade-in">
                <h3>Repudiandae, error?</h3>
                <p>
                    Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laborum
                    quasi quis doloribus quia illum laudantium.
                </p>
            </div>
        </TransitionFadeIn>  
    </div>

    </Observer>

</template>
<script setup>
import TransitionFadeIn from '../components/TransitionFadeIn.vue';
import Observer from './Observer.vue';
import {ref} from 'vue'
const observerOptions = {
    root: null,
    threshold: 0.5,
}
const isShowFadeIn = ref(false)

</script>
<style scoped>
.columns {
  display: flex;
}


</style>

