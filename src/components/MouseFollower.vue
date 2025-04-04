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
  width: 50px;
  height: 50px;
  box-shadow: 0px 0px 4px #222c;
  
  border-radius: 50%;
  position: fixed;
  top: -15px;
  left: -20px;
  pointer-events: none;
  z-index: 9999;
  mix-blend-mode: hard-light;
}

</style>