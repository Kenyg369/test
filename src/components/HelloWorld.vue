<template>
  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>

  <input type="text" placeholder="firstname" :value="firstName" @input="nameUpdate('firstName', $event.target.value)">
  <input type="text" placeholder="lastname" :value="lastName" @input="nameUpdate('lastName', $event.target.value)">

  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { reactive } from 'vue'
const emit =defineEmits(["update:firstName","update:lastName"])
const nameUpdate = (propName,val) => {emit(`update:${propName}`, val)} 

const props = defineProps({
  firstName: String,
  lastName: String,
})

const state = reactive({ count: 0 })
</script>

<style scoped>
a {
  color: #42b983;
}
</style>


/* 
<input type="text" placeholder="firstname" :value="firstName" @input="firstNameUpdate($event.target.value)">
<input type="text" placeholder="lastname" :value="lastName" @input="lastNameUpdate($event.target.value)">

const firstNameUpdate = (val) => {emit("update:firstName", val)} 
const lastNameUpdate = (val) => {emit("update:lastName", val)}  */