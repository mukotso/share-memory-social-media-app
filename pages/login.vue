<template>
  <div class="login">
    <h2>WELCOME BACK</h2>
    <form @submit.prevent="loginUser()">
      <div class="p-field">
        <label for="username">Email:</label>
        <InputText type="email" v-model="formData.email" />
      </div>

      <div class="p-field">
        <label for="username">Password:</label>
        <InputText type="password" v-model="formData.password" />
      </div>
     
      <button type="submit" class="p-button p-button-primary">LOGIN</button>
    </form>
    <router-link to="/register">Don't have an account? Register here.</router-link>
  </div>
</template>

<script setup>
import InputText from 'primevue/inputtext'
import {ref} from 'vue' 
import axios  from 'axios'
const formData = ref({
    email : "",
    password : ""
})

const loginUser = ()=>{
axios.post('/login', {formData}) .then((response)=>{

}).catch( (error) => {

})
}

</script>

<style scoped>
@import '~/static/css/styles.css';

.login {
     padding: 20% 30%;
     width: 80%;
     margin:auto;
 }
</style>