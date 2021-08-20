<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorldInput 
  v-model:firstName="firstName" 
  v-model:lastName="lastName"  
  />
  
  <span>My name is {{firstName + lastName}}</span>


</template>

<script setup>
import {ref} from "vue"
import HelloWorldInput from './components/HelloWorld.vue'

const firstName = ref("firstName"); 
const lastName = ref("lastName");


</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

/*   
  v-model:firstname="firstName" 
  v-model:lastname="lastName"  
*/


/* 
  :firstName="firstName"
  @update:firstName = "firstName = $event"
  :lastName="lastName"
  @update:lastName = "lastName = $event"
 */