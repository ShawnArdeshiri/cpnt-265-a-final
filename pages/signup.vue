<template>
  <div>

    <body>
		<div class="container">
    <h1 class="label">Sign up </h1>
    <form class="signup_form" @submit.prevent="signIn">
      <div class="font">Email</div>
        <input type="text" id="email" name="email" required v-model="email">
        <div class="font font2">Password</div>
        <input type="password" id="password" name="password" required v-model="password">

      <div class="buttons">
        <button @click="signUp">Sign Up</button>
        <button @click="signIn">Login</button>
      </div>
    </form>
</div>
</body>
  </div>
  
    
	


</template>

<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
const router = useRouter(); 
const user = useSupabaseUser();
const client = useSupabaseClient();
const email = ref('');
const password = ref('');

if(user.value)
{
  router.push('')
}


async function signUp() {
  try
  {
    const { data, error } = client.auth.signUp({
      email: email.value,
      password: password.value
    });

    if(error)
    {
      throw error;
    } 
    
    else
    {
      router.push('/login');
    }
  }

  catch(error)
  {
    console.error(error);
  }
}

async function signIn() {
  try 
  {
    const { data, error } = await client.auth.signInWithPassword({
      email: email.value,
      password: password.value
    });

    if(error)
    {
      throw error;
    } 
    
    else
    {
      router.push('/about');
    }
  } 
  
  catch(error) 
  {
    console.error(error);
  }
} 


</script>

<style scoped>
body {
 background: url(/assets/images/giphy.gif) no-repeat;
 background-size: cover;
 align-items: center;
 justify-content: center;
 display: flex;
 font-family: sans-serif;
}

.container{
	position: relative;
	margin-top: 100px;
	width: 450px;
	height: auto;
	background: #dedede;
	border-radius: 5px;

  
}
.label{
	padding: 20px 160px;
	font-size: 35px;
	font-weight: bold;
	color: #130f40;
}
.signup_form{
	padding: 20px 40px;
}
.signup_form .font{
	font-size: 18px;
	color: #130f40;
	margin: 5px 0;
}
.signup_form input{
	height: 40px;
	width: 350px;
	padding: 0 5px;
	font-size: 18px;
	outline: none;
	border: 1px solid silver;
}
.signup_form .font2{
	margin-top: 30px;
}
.signup_form button{
	margin: 45px 0 30px 0;
	height: 45px;
	width: 365px;
	font-size: 20px;
	color: white;
	outline: none;
	cursor: pointer;
	font-weight: bold;
	background: #1A237E;
	border-radius: 3px;
	border: 1px solid #3949AB;
	transition: .5s;
}
.signup_form button:hover{
	background: #151c6a;
}

</style>