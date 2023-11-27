<template>
     <div>
          <div class="bg-red-200 p-4">
               <Menubar :model="items">
                    <template #start>
                         <h1>MEMORIES HUB</h1>
                    </template>
                    <template #end>
                         <a href="/profile"> <i class="pi pi-fw pi-user"></i>Account</a>
                        <a href="/login"><Button class="p-button-sm p-button-warning" > <i class=" pi pi-fw pi-power-off"></i>Logout</Button></a> 
                    </template>
               </Menubar>
          </div>
          <div class="content">
                <slot></slot>
          </div>
     </div>
   
 </template>
 
 <script setup>
 import Menubar from 'primevue/menubar';
 import Button from 'primevue/button/Button';
 import '../static/css/styles.css'
 const   items = [
                 {
                    label:'All Posts',
                    icon:'pi pi-fw pi-file',
                    to:"/posts"
                 }]
 </script>

 <style>
 .content{
     margin:2%  5%;
 }
</style>