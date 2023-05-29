<script setup>
import { ref } from 'vue';
const first_name = ref('')
const last_name = ref ('')
const email = ref('')
const confirm_email = ref('')
const password = ref('')
const confirm_password = ref('') 

const handleSubmit = () => {
  if (confirm_email.value !== email.value){
    console.log("email  dont match")
  return;
  }
  
  if(confirm_password.value !== password.value){
    console.log("Password dont match")
    return;
  }
  console.log(first_name.value)
  console.log(last_name.value)
  console.log(email.value)
  console.log(confirm_email.value)
  console.log(password.value)
  console.log(confirm_password.value)
  }





</script>

<template>
  <h2>Sign Up</h2>
  <form @submit.prevent="handleSubmit">
    <label>First Name:  </label>
    <input type="text" placeholder="Enter your First Name:" v-model="first_name">
    <br>
    <br>

    <label>Last Name:  </label>
    <input type="text" placeholder="Enter your Last Name:" v-model="last_name">
    <br>
    <br>

    <label>Email:  </label>
    <input type="email" placeholder="Enter your email:" v-model="email">

    <br>
    <br>

    <label>Confirm Email:  </label>
    <input type="email" placeholder="Re-enter your Email:" v-model="confirm_email">
    <div v-if="email != confirm_email" class="text-danger">Email does'nt Match</div>
    <br>
    <br>

    <label>Password:</label>
    <input type="password" placeholder="Enter your Password:" v-model="password">
    <br>
    <br>

    <label>Confirm:  </label>
    <input type="password" placeholder="Re-enter your Password:" v-model="confirm_password">
    <div v-if="password != confirm_password" class="text-danger">Password does'nt Match</div>
    <br>
    <br>

    <button type="submit">Submit</button>
  </form>

</template>