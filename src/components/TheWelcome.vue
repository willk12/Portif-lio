<template>
  <div class="w-full h-full">
    <h1 class="text-gray-600 text-4xl text-center split opacity-0">Olá meu nome é William 👋🏼</h1>
    <h2 class="text-gray-400 text-2xl text-center split opacity-0">Web Designer & Desenvolvedor Front-End</h2>
  </div>

  <div class="w-full flex justify-center items-center">
    <img src="./photos/profile-animated.png" alt="" class="w-[400px] h-[600px] rounded-full" />
    <div
      class="h-[400px] rounded-lg p-1 mt-4 w-[60%] overflow-hidden relative text-3xl text-gray-600 left-1 text-center"
    >
      <div
        class="moveOn midTitle h-full m-auto p-1 bg-white rounded flex flex-col gap-2 justify-center"
      >
       <div class="flex flex-col gap-2 justify-center p-4 bg-white w-full h-full relative rounded">
         <p><strong>Oi, tudo bem?</strong></p>
        <p>Me chamo William Almeida Lima e tenho 28 anos!</p>
        <p>
          Atualmente, estou me aprofundando em Vue.js e Tailwind CSS sempre buscando evoluir
          tecnicamente e encarar novos desafios.
        </p>
        <p>
          Sou apaixonado por design e tecnologia, gosto de trabalhar em equipe e acredito no poder
          da troca de conhecimento para crescer junto.
        </p>
       </div>
      </div>
    </div>
  </div>

  <div class="w-full flex justify-center items-center mt-[100px] moveOn">
    <ul class="text-2xl font-bold flex gap-4 text-gray-600 cursor-pointer">
      <li>📝Ver Portifólio</li>
      <li>📞Fale Comigo</li>
      <li>💪Ver Skills</li>
    </ul>
  </div>

  <div class="px-[200px] mt-24 moveOn">
    <h2 class="text-gray-600 text-3xl">Minhas Especialidades</h2>

    <ul class="list-disc text-gray-600 text-2xl mt-4">
      <li>Front-End Moderno (Vue, React, Tailwind, GSAP)</li>
      <li>Design Responsivo e UX/UI</li>
      <li>Animações e Interatividade</li>
      <li>Metodologias Ágeis</li>
    </ul>
  </div>

  <div class="px-[200px] mt-24 flex flex-col justify-end items-end moveOn">
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

gsap.registerPlugin(SplitText);

console.clear();

document.fonts.ready.then(() => {
  gsap.set(".split", { opacity: 1 });

  const split = SplitText.create(".split", {
    type: "words",
    wordsClass: "word++",
    wordDelimiter: String.fromCharCode(8205)
  });

  gsap.from(split.words, {
    y: -100,
    opacity: 0,
    rotation: "random(-80, 80)",
    stagger: 0.1,
    duration: 1,
    ease: "back"
  });
});

</script>

<style scoped lang="scss">
.midTitle {
  &::before {
    content: '';
    position: absolute;
    /* top: -50px; */
    left: -425px;
    width: 2146px;
    height: 1495px;
    /* border-radius: 50%; */
    background: linear-gradient(270deg, #42d392, #42d392, #647eff);
    animation: gradientShift-14d3142e 3s ease-in-out infinite;
    z-index: -1;
  }
}

.gradient-circle {
  background: linear-gradient(270deg, #42d392, #42d392, #647eff);
  animation: gradientShift-14d3142e 3s ease-in-out infinite;
  left: -84%;
  top: -81%;
  width: 3000px;
  height: 3000px;
}

.moveOn {
  animation: moveIn;
  animation-duration: 1.5s;
  animation-fill-mode: forwards;
  animation-timing-function: ease-in-out;
}

@keyframes moveIn {
  from {
    transform: translateY(0px);
  }
}

@keyframes gradientShift {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
