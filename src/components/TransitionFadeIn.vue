<template>
 <Transition :appear="appear">
   <slot v-if="props.isShow"></slot>
 </Transition>
</template>
<script setup>
import { defineProps } from 'vue';
const props = defineProps({
    appear: {
      type: Boolean
    },
    isShow: {
      type: Boolean
    }

})

</script>

<style scoped>
.v-enter-active,
.v-leave-active { 
  transition: opacity 0.5s 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

.v-enter-to,
.v-leave-from {
  opacity: 1;
}
</style>