<script setup>
import { ref } from 'vue'
const title = ref('Mega Ejemplo')
const solicitudes = ref (0)
const incrementar = () => {
  solicitudes.value++
}
const decrementar = () => {
  if(solicitudes.value > 0){
    solicitudes.value--
  }
  
}


</script>

<template>
  <h2>{{ title }}</h2>
 <div class="user">
  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="w-6 h-6">
  <path strokeLinecap="round" strokeLinejoin="round" d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 
  0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z" />
  </svg>


  <div v-if="solicitudes > 0 "  
    class="notification">
    {{ solicitudes }}
  </div>
 
 </div>
 <span @click="incrementar">+</span>
  <span @click="decrementar">-</span>

<div v-show="solicitudes > 0">
  wooho!! tengo solicitudes
</div>

<input type="text " v-model="title">

</template>

<style scoped>
.span{
background: orange;
display: inline-block;
width: 24px;
height: 24px;
text-align: center;
margin: 10px;
border-radius: 4px;

}
span:hover{
 background: rgb(97, 96, 96);
 cursor: pointer;
}
 .user{
  position: relative;
  width: 40px;
  height: 40px;
  background: green;
 }

 .notification{
  position: absolute;
  top: -12px;
  right: -12px;
  background-color: red;
  color: white;
  border-radius: 50%;
  width: 24px;
  height: 24px;
  text-align: center;
 }

</style>
