<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MouseFollower from './components/MouseFollower.vue';

</script>

<template>
  <MouseFollower />
  <div class="h-[166px]">
    <header class="w-full bg-gray-600 py-3  navbar">
   

   <div class="w-full">
    

     <nav class=" text-2xl  flex gap-8 px-3 justify-end absolute text-white menu">
       <RouterLink to="/" >Home</RouterLink>
       <RouterLink to="/about">Sobre</RouterLink>
     </nav>
   </div>
 </header>
  </div>

  <RouterView />
</template>

<style scoped>

.navbar{

  position: absolute;
    transform: rotate(4deg);
    height: 170px;
    top: -72px;
    left: -10px;
    width: 103%;

}

.menu {
    position: relative;
    top: 130px;
    right: 53px;
    transform: rotate(-3deg);
}


</style>
