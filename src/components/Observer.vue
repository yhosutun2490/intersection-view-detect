<template>
    <div class="observer-wrap" ref="target">
        <slot></slot>
    </div>
</template>
<script setup>
import {ref,onMounted, defineEmits,defineProps,onBeforeUnmount} from 'vue'
const target = ref(null)
const observer = ref(null)
const emits = defineEmits(['is-in-view', 'is-outside-view'])
const props = defineProps({
    observerOptions: {
        type: Object
    }

})


// mounted 將容器掛載observer實例
onMounted(()=>{
    observer.value = new IntersectionObserver((entries)=>{
      // 偵測是否進入view port
      if (entries[0].isIntersecting) {
        emits("is-in-view")
        console.log("element in view")
      }
      else {
        emits('is-outside-view')
        console.log("element out of view")
      }

    },props.observerOptions)
    observer.value.observe(target.value);
})

// 卸載監聽器
onBeforeUnmount(()=>{
    observer.value.disconnect()
})


</script>