<template>
<Navbar />
<body>



<section class="box">
  <div class="rules">
  <div class="how">
    <h1>HOW TO PLAY</h1>  
  </div>
   <div class="text_rule">
    <p>Players take turns rolling the dice.
     On your turn, you can roll the dice multiple times to accumulate points for that turn.
     On your turn, roll the dice. The numbers rolled on the dice are added to your current turn score.</p>
     <p class="red">If you roll a 1 Your turn score becomes 0, Your turn ends, and it's the next player's turn.</p><p>If you decide to Hold Your turn score is added to your total score and It's the next player's turn. </p>
     <p> Pressing the "bonus" button triggers the generation of a random true or false question. If answered correctly, 50 points are added to the player's score.</p>
     <p>The first player to reach the 100 points or more wins the game.</p>
    </div>
  </div>
  <div class="picture">
    <img src="/assets/images/Screenshot (16).png">
  </div>
</section> 
</body>
<Footer />
</template>

<script setup>

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=Shadows+Into+Light&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Jersey+10+Charted&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=Shadows+Into+Light&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Amatic+SC:wght@400;700&family=Inter:wght@100..900&family=Jersey+10+Charted&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=Shadows+Into+Light&display=swap');



body {
  margin: 0;
  padding: 0;
  background-color: black;
}

img {
  padding-top: 10rem;
  height: 200px;
}

.box{
  width: 100%;
  display: flex
}
.red{
  color: red;
}

.rules {
  width: 50%;
  height: 100%;
  margin: 0;
  padding-left: 100px;
}
.picture{
  margin: 0px;
  width: 400px;
  padding: 120px; 

  
}
.picture img {

  width: 450px;
  height: 80%;
}

h1 { 
  color: white;
  font-size: 100px;
  font-family: "Jersey 10 Charted", sans-serif;
  font-weight: 400;
  font-style: normal;
}
.how{
  padding-bottom: 0px;
}
.text_rule{
  margin: 0;
  max-width: 450px;
}
p {
  color: #fff;
  font-size: 30px;
  font-family: "Amatic SC", sans-serif;
  font-weight: 400;
  font-style: normal;
}


</style>