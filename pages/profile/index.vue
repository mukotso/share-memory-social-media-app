<template>
    <Default>
        <template>
            <div class="profile bg-red-200">
                
                <div class="user-info">
                    <img src="../../static/images/old.jpeg" alt="User Avatar" class="avatar" />
                    <h2> {{ formData.name }}</h2>
                    <!-- <p>Email: {{ user.email }}</p>
                    <p>Username: {{ user.username }}</p>
                    <p>Phone Number: {{ user.phone }}</p> -->

                    <form @submit.prevent="updateProfile()">

                        <div class="p-field">
                        <label for="firstname">FirstName:</label>
                        <InputText type="text" v-model="formData.firstName" />
                        </div>


                        <div class="p-field">
                        <label for="lastname">LastName:</label>
                        <InputText type="text" v-model="formData.lastName" />
                        </div>

                        <div class="p-field">
                        <label for="email">Email:</label>            
                        <InputText type="email" v-model="formData.email" />
                        </div>

                        <div class="p-field">
                        <label for="username">Username:</label>
                        <InputText type="text" v-model="formData.username" />
                        </div>

                        <div class="p-field">
                        <label for="phone">Phone Number:</label>
                        <InputText type="number" v-model="formData.phone" />
                        </div>

                        <button type="submit" class=" mt-4 p-button p-button-success">UPDATE DETAILS</button>
                </form>

                </div>
            </div>
        </template>
    </Default>
  </template>
  
  
  <script setup>
   import Default from '../../components/Default.vue';
   import {ref} from 'vue'
  import InputText from 'primevue/inputtext/InputText';
   const formData = ref({
        email : "kelvinmukotso@gmail.com",
        username:"mukotso",
        firstName: "Kelvin",
        lastName: "Mukotso",
        phone: "254789546783",
    })

    const updateProfile = ()=>{

    }

  </script>
  
  <style scoped>
  .profile {
    border-radius: 20px;
    padding: 30px;
    display: flex;
    align-items: center;
    margin:2% 20%;
  }


  
  .avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    margin-right: 20px;
  }
  
 
  
  </style>
  