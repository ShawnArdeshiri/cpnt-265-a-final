<template>
  
  <body>
    <main>
      <div></div>
      <section class="player player--0 player--active" ref="player0El">
        <h2 class="name" id="name--0">Player 1</h2>
        <p class="score" id="score--0">43</p>
        <div class="current">
          <p class="current-label">Current</p>
          <p class="current-score" id="current--0">0</p>
        </div>
      </section>
      <section class="player player--1" ref="player1El">
        <h2 class="name" id="name--1">Player 2</h2>
        <p class="score" id="score--1">24</p>
        <div class="current">
          <p class="current-label">Current</p>
          <p class="current-score" id="current--1">0</p>
        </div>
      </section>

      <img src="/assets/images/dice-5.png" alt="Playing dice" class="dice" ref="diceEl"/>
      <button class="btn btn--new" ref="btnNew" @click="">🔄 New game</button>
      <button class="btn btn--roll" ref="btnRoll" @click="">🎲 Roll dice</button>
      <button class="btn btn--hold" ref="btnHold"@click="">📥 Hold</button>
      <button class="btn btn--bonus" ref="btnBonus">🎁 Bonus</button>
      
      

    </main>
  </body>
</template>



<script setup>
import { ref, onMounted } from 'vue'

//selecting elements

const player0El = ref(null)
const player1El = ref(null)
const diceEl = ref(null)
const btnNew = ref(null)
const btnHold = ref(null)
const btnRoll = ref(null)
onMounted(() => {
  const score0El = document.getElementById('score--0')
  const score1El = document.getElementById('score--1');
  const current0El = document.getElementById('current--0');
  const current1El = document.getElementById('current--1');
  
  const init = function () {
  scores = [0, 0];
  currentScore = 0;
  activePlayer = 0;
  playing = true;

  score0El.textContent = 0;
  score1El.textContent = 0;
  current0El.textContent = 0;
  current1El.textContent = 0;

};
init();
});

let scores, currentScore, activePlayer, playing;



</script>







<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html {
  font-size: 62.5%;
  box-sizing: border-box;
}

body {
  font-family: 'Nunito', sans-serif;
  font-weight: 400;
  height: 110vh;
  color: #333;
  background-image: linear-gradient(to top left, #753682 0%, #2e57bf 100%);
  display: flex;
  align-items: center;
  justify-content: center;
}

/* LAYOUT */
main {
  position: relative;
  width: 100%;
  height: 70%;
  background-color: rgba(255, 255, 255, 0.35);
  backdrop-filter: blur(200px);
  filter: blur();
  box-shadow: 0 40px 70px rgba(0, 0, 0, 0.25);
  border-radius: 9px;
  overflow: hidden;
  display: flex;
}

.player {
  flex: 50%;
  padding: 90px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: all 0.75s;
}

/* ELEMENTS */
.name {
  position: relative;
  font-size: 50px;
  text-transform: uppercase;
  letter-spacing: 1px;
  word-spacing: 2px;
  font-weight: 300;
  margin-bottom: 10px;
}

.score {
  font-size: 40px;
  font-weight: 300;
  color: #c7365f;
  margin-bottom: auto;
}

.player--active {
  background-color: rgba(255, 255, 255, 0.4);
}
.player--active .name {
  font-weight: 400;
}
.player--active .score {
  font-weight: 400;
}

.player--active .current {
  opacity: 1;
}

.current {
  background-color: #c7365f;
  opacity: 0.8;
  border-radius: 9px;
  color: #fff;
  width: 40%;
  padding: 30px;
  text-align: center;
  transition: all 0.75s;
}

.current-label {
  text-transform: uppercase;
  margin-bottom: 10px;
  font-size: 20px;
  color: #ddd;
}

.current-score {
  font-size: 30px;
}

/* ABSOLUTE POSITIONED ELEMENTS */
.btn {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  color: #444;
  background: none;
  border: none;
  font-family: inherit;
  font-size: 20px;
  text-transform: uppercase;
  cursor: pointer;
  font-weight: 400;
  transition: all 0.2s;

  background-color: white;
  background-color: rgba(255, 255, 255, 0.6);
  backdrop-filter: blur(10px);

  padding: 5px 15px;
  border-radius: 50rem;
  box-shadow: 0 15px 50px rgba(0, 0, 0, 0.1);
}

.btn::first-letter {
  font-size: 30px;
  display: inline-block;
  margin-right: 10px;
}

.btn--new {
  top: 20px;
}
.btn--roll {
  top: 300px;
}
.btn--hold {
  top: 400px;
}
.btn--bonus {
top:500px;
}

.btn:active {
  transform: translate(-50%, 3px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
}

.btn:focus {
  outline: none;
}

.dice {
  position: absolute;
  left: 50%;
  top: 150px;
  transform: translateX(-50%);
  height: 100px;
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.2);
}

.player--winner {
  background-color: #2f2f2f;
}

.player--winner .name {
  font-weight: 700;
  color: #c7365f;
}

.hidden {
  display: none;
}

</style>