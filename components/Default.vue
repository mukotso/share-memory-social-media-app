<template>
     <div>
          <div class="bg-red-400 p-4">
               <Menubar :model="items">
                    <template #start>
                         <h1>MEMORIES HUB</h1>
                    </template>
                    <template #end>
                         <a href="/profile"> <i class="pi pi-fw pi-user"></i>Account</a>
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
 const   items = [
                 {
                    label:'All Posts',
                    icon:'pi pi-fw pi-file',
                 }]
 </script>

 <style>
 .content{
     margin:2%  5%;
 }
</style>