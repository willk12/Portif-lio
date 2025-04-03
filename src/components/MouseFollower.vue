<template>
    <div class="ball" ref="ball">

    </div>
</template>

<script setup>
import gsap from 'gsap';
import { onMounted, onUnmounted, ref } from 'vue';

const ball= ref(null)

const moveball = (event)=>{
    gsap.to(ball.value,{
        x: event.clientX,
        y: event.clientY,
        duration: 0.9,
        ease: "power2.out"
    });
}




onMounted(()=>{
    window.addEventListener("mousemove", moveball);
})

onUnmounted(() => {
  window.removeEventListener("mousemove", moveball);
});

</script>

<style lang="scss" scoped>
.ball {
  width: 100px;
  height: 100px;
  background-color: #4a5565;
  box-shadow: 1px 2px 2px 0px black;
  border-radius: 50%;
  position: fixed;
  top: -5px;
  left: 0;
  pointer-events: none;
  z-index: 9999;
  mix-blend-mode: difference;
}

</style>