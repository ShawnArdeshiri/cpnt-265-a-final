<template>
  <body>
    <div class="container" >
  <main>
    <div class="left-side">
      <h1>Welcome</h1>
      <p class="sub-heading"></p>
      <a href="about"><button><h2>PLAY NOW</h2></button></a>
      <button><h2>SIGN UP</h2></button>
    </div>

    <div class="cube-container">
      <div class="cube"  >
        <div class="cube-face front"><img src="/assets/images/dice-6.png"></div>
        <div class="cube-face back"><img src="/assets/images/dice-1.png"></div>
        <div class="cube-face left"><img src="/assets/images/dice-2.png"></div>
        <div class="cube-face right"><img src="/assets/images/dice-5.png"></div>
        <div class="cube-face top"><img src="/assets/images/dice-4.png"></div>
        <div class="cube-face bottom"><img src="/assets/images/dice-3.png"></div>
      </div>
    </div>
  </main>
    </div>
</body>
</template>

<script setup>

import { ref, onMounted } from 'vue';

const cube = ref(null);
const rotationValue = 270;
let mouseX = 0;
let mouseY = 0;

const handleMouseMove = (event) => {
  mouseX = event.clientX;
  mouseY = event.clientY;
  const rotateX = -(mouseY / window.innerHeight - 0.5) * rotationValue;
  const rotateY = (mouseX / window.innerWidth - 0.5) * rotationValue;
  cube.value.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg)`;
};

onMounted(() => {
  cube.value = document.querySelector(".cube");
  window.addEventListener("mousemove", handleMouseMove);
});
</script>

<style scoped>

:root {
  --cube-width: 300px;
  --translateZ: 150px;

}
body {
  margin: 0;
  padding: 0;
  height: 100vh;
  background-color: black;
  font-family: "Poppins", sans-serif;
  }

  main {
 color: #eee;
 display: flex;
 align-items: center;
 height: 100vh;
 justify-content: space-between;

}

button {
  width: 200px;
   margin: 1rem;
   border-radius: 50px;
}

.container {
  max-width: 1000px;
  margin: 0 auto;
}

.cube-container{
perspective: 1000px;
}

.cube-container .cube {
  width: 200px;
  height: 200px;
  transform-style:preserve-3d;
}



main h1 {
  margin: 0;
  font-size: 100px;
}

main .sub-heading {
  font-size: 24px;
  margin: 0 ;
}

.cube-container .cube-face {
width: 300px;
height: 300px;
position: absolute;
font-size: 30px;
display: flex;
align-items: center;
justify-content: center;
}

.cube-container .front {
  transform: translateZ(150px);
}

.cube-container .back {
  transform: rotateY(180deg) translateZ(150px);
}

.cube-container .left {
  transform: rotateY(-90deg) translateZ(150px);
}
.cube-container .right {
  transform: rotateY(90deg) translateZ(150px);
}
.cube-container .top {
  transform: rotateX(90deg) translateZ(150px);
}
.cube-container .bottom {
  transform: rotateX(-90deg) translateZ(150px);
}
</style>

