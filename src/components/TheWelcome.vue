<template>
  <div class="w-full h-full">
    <h1 class="text-gray-600 text-4xl text-center">Olá meu nome é William 👋🏼</h1>
    <h2 class="text-gray-400 text-2xl text-center">Web Designer & Desenvolvedor Front-End</h2>
  </div>

  <div class="w-full flex justify-center items-center">
    <img src="./photos/profile-animated.png" alt="" class="w-[400px] h-[600px] rounded-full" />
    <div
      class="bg-white rounded-lg p-4 mt-4 w-[40%] flex flex-col text-3xl text-gray-600 relative left-1 text-center"
    >
      <p>Olá tudo bem, me chamo William tenho 28 anos</p>
      <p>
        Sou um desenvolvedor Front-End e Web Designer, atualmente estou estudando Vue.js e Tailwind
        CSS
      </p>
      <p>
        Estou sempre em busca de novos desafios e aprendizados, gosto de trabalhar em equipe e
        compartilhar conhecimento
      </p>
    </div>
  </div>

  <div class="w-full flex justify-center items-center mt-[100px]">
    <ul class="text-2xl font-bold flex gap-4 text-gray-600 cursor-pointer">
      <li>📝Ver Portifólio</li>
      <li>📞Fale Comigo</li>
      <li>💪Ver Skills</li>
    </ul>
  </div>

  <div class="px-[200px] mt-24">
    <h2 class="text-gray-600 text-3xl">Minhas Especialidades</h2>

    <ul class="list-disc text-gray-600 text-2xl mt-4">
      <li>Front-End Moderno (Vue, React, Tailwind, GSAP)</li>
      <li>Design Responsivo e UX/UI</li>
      <li>Animações e Interatividade</li>
      <li>Metodologias Ágeis</li>
    </ul>
  </div>

  <div class="px-[200px] mt-24 flex flex-col justify-end items-end">
    <h2 class="text-gray-600 text-3xl mr-[9%]">Minhas Skills</h2>

    <ul class="list-disc text-gray-600 text-2xl mt-4">
      <li>HTML, CSS, JavaScript</li>
      <li>Vue.js, React</li>
      <li>Tailwind, GSAP</li>
      <li>Git flow, Metodologias Ágeis</li>
    </ul>
  </div>
</template>
<script setup lang="ts">
import gsap from 'gsap'
</script>

<style scoped></style>
