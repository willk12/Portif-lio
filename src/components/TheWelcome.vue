<template>
  <div class="w-full h-full">
    <div class="flex justify-center items-center">
      <h1 class="text-gray-600 text-4xl text-center split">Olá meu nome é William</h1>
      <h2 class="text-4xl">😁</h2>
    </div>
    <h2 class="text-gray-600 text-2xl text-center split">Web Designer & Desenvolvedor Front-End</h2>
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

  <div class="w-full flex justify-center items-center mt-[100px]">
    <ul class="text-2xl font-bold flex gap-4 text-white cursor-pointer justify-center items-center">
      <li class="bg-gray-400 p-2 rounded flex gap-2 transform">
        <div><img src="./photos/wirte.png" alt="" class="w-[40px] transform-revert" /></div>
        <div class="transform-revert">Ver Portifólio</div>
      </li>
      <li class="bg-gray-400 p-4 rounded flex gap-2 transform">
        <div><img src="./photos/muscle.png" alt="" class="w-[40px] transform-revert" /></div>
        <div class="transform-revert">Ver Skills</div>
      </li>
      <li class="bg-gray-500 p-2 rounded flex gap-2 transform">
        <div>
          <img src="./photos/telephone-call.png" alt="" class="w-[40px] transform-revert" />
        </div>
        <div class="transform-revert">Fale Comigo</div>
      </li>
    </ul>
  </div>
  ''
  <div class="mb-2">
    <div
      class="px-[200px] mt-24 mb-1 bg-gray-600 text-white p-4 w-400 -left-10 relative transform fade-left"
    >
      <h2 class="text-3xl transform-revert">Minhas Especialidades</h2>

      <ul class="text-shadow-xs text-shadow-black text-2xl mt-4 transform-revert relative -left-4 ">
        <li>Front-End Moderno (Vue, React, Tailwind, GSAP)</li>
        <li>Design Responsivo e UX/UI</li>
        <li>Animações e Interatividade</li>
        <li>Metodologias Ágeis</li>
      </ul>
    </div>
    <div
      class="px-[200px] p-4 flex flex-col justify-end items-end bg-gray-600 text-white w-400 relative -right-100 transform  fade-right "
    >
      <h2 class="text-3xl mr-[9%] transform-revert relative -left-3">Minhas Skills</h2>

      <ul class="text-shadow-xs text-2xl mt-4 transform-revert">
        <li>HTML, CSS, JavaScript</li>
        <li>Vue.js, React</li>
        <li>Tailwind, GSAP</li>
        <li>Git flow, Metodologias Ágeis</li>
      </ul>
    </div>
  </div>
</template>
<script setup lang="ts">
import { onMounted } from 'vue'
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

onMounted(() => {
  const splits = document.querySelectorAll('.split')

  splits.forEach((split) => {
    const chars = split.textContent?.split('') || []
    split.textContent = ''

    chars.forEach((char) => {
      const span = document.createElement('span')
      span.textContent = char === ' ' ? '\u00A0' : char
      span.style.display = 'inline-block'
      split.appendChild(span)
    })

    const spanChars = split.querySelectorAll('span')

    gsap.from(spanChars, {
      duration: 0.8,
      y: 40,
      opacity: 0,
      ease: 'power2.out',
      stagger: 0.05,
    })
  })

// efeito 3D sutil na esquerda
gsap.from(".fade-left", {
  opacity: 0,
  x: -100,
  rotateY: -15, // inclina como se viesse de trás
  skewY: 2,
  duration: 1.5,
  ease: "power3.out",
  scrollTrigger: {
    trigger: ".fade-left",
    start: "top 80%",
    toggleActions: "play none none reverse"
  }
});

// efeito 3D sutil na direita
gsap.from(".fade-right", {
  opacity: 0,
  x: 100,
  rotateY: 15,
  skewY: -2,
  duration: 1.5,
  ease: "power3.out",
  scrollTrigger: {
    trigger: ".fade-right",
    start: "top 80%",
    toggleActions: "play none none reverse"
  }
});
})
</script>

<style scoped lang="scss">

.fade-left, .fade-right {
  will-change: transform, opacity;
}

.transform {
  transform: skew(10deg);
}

.transform-revert {
  transform: skew(-10deg);
}

.midTitle {
  &::before {
    content: '';
    position: absolute;
    /* top: -50px; */
    left: -425px;
    width: 2146px;
    height: 1495px;
    /* border-radius: 50%; */
    background: linear-gradient(270deg, #dedede, #ffffff, #727272);
    animation: gradientShift-14d3142e 3s ease-in-out infinite;
    z-index: -1;
  }
}

.gradient-circle {
  background: linear-gradient(270deg, #ffffff, #000000, #ffffff);
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
