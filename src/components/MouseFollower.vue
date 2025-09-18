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
        duration: 1.5,
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
  box-shadow: 0px 0px 10px 10px rgb(0, 0, 0);
  background-color:#f3f4f6;
  border-radius: 50%;
  position: fixed;
  top: -15px;
  left: -20px;
  pointer-events: none;
  z-index: 9999;
  mix-blend-mode: normal;
  background: linear-gradient(45deg, #42444441, #ffffff6e);
}

</style>