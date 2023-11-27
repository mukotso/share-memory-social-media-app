<template> 
    <div class="register">
      <h2>CREATE AN ACCOUNT</h2>
      <form @submit.prevent="registerUser()">

        <div class="p-field">
          <label for="username">FirstName:</label>
          <InputText type="text" v-model="formData.firstName" />
        </div>


        <div class="p-field">
          <label for="username">LastName:</label>
          <InputText type="text" v-model="formData.lastName" />
        </div>

        <div class="p-field">
          <label for="username">Email:</label>
          <InputText type="email" v-model="formData.email" />
        </div>

        <div class="p-field">
          <label for="username">Username:</label>
          <InputText type="text" v-model="formData.username" />
        </div>

        <div class="p-field">
          <label for="username">Phone Number:</label>
          <InputText type="number" v-model="formData.phone" />
        </div>
  
        <div class="p-field">
          <label for="username">Password:</label>
          <InputText type="password" v-model="formData.password" />
        </div>

        <div class="p-field">
          <label for="username">Confirm Password:</label>
          <InputText type="password" v-model="formData.password" />
        </div>
       
        <button type="submit" class="p-button p-button-primary">REGISTER</button>
      </form>
      <router-link to="/login">Already have an account? Login here.</router-link>
    </div>
  </template>

  <script setup>
    import InputText from 'primevue/inputtext'
    import {ref} from 'vue' 
    import axios from 'axios'

    const formData = ref({
        email : "",
        password: "",
        username:"",
        firstName: "",
        lastName: "",
        phone: "",
        image:"",
        images:[]
    })

    const registerUser = ()=>{
        axios.post('/login', {formData}) .then((response)=>{

        }).catch( (error) => {

        })
}

</script>

<style>
@import '~/static/css/styles.css';

.register {
     padding: 5% 25%;
     width: 80%;
     margin:auto;
 }
</style>