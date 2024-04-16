<template>
  <body>
  <main> 
<div class="banner">
    <nav class="navbar">
     
      <ul>
       <li><a href="/main">Home</a></li>
       <li><a href="https://dice-game-tau-tan.vercel.app/">Play</a></li>
       <li><a href="/about">About</a></li> 
      </ul>
    </nav>
  </div>
</main> 
</body>
</template>

<script setup>

</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&family=Shadows+Into+Light&display=swap');

body {
  margin: 0;
  padding: 0;
  background-color: black;
}
.banner {
  width:100%;
  height:100px;
  background-image:linear-gradient(rgba(0,0,0,0.75),rgba(0,0,0,0.75));
  background-position: 0% 0%;
  background-size: cover;
  min-height: 100px;
}

main {
display: flex;
justify-content: space-between;


}



li {
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  font-style: normal;
  font-size: 20px;
  font-weight: 300;
  color: antiquewhite;
}

.navbar {
  width:30%;
  margin: auto;
  padding: 35px 0;
  display: flex;
  justify-content:space-between;

}

.logo {
   width: 100px;
   cursor: pointer;
}

nav ul li {
  list-style: none;
  display: inline-block;
  margin: 40px;
  position: relative;
}

li a {
  text-decoration: none;
  color: #fff;
}

nav ul li::after{
  content:'';
  height:3px;
  width:0;
  background:#009688;
  position: absolute;
  left: 0px;
  bottom: -10px;
  transition: 0.5s;
}
nav ul li:hover::after {
width: 100%;
}
</style>