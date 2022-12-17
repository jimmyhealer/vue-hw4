<script setup>
import { ref } from 'vue'

const name = ref('')
const age = ref(-1)

name.value = prompt('Please input your name:')
let input_years = parseInt(prompt('Please input your birth year:'))
age.value = (new Date()).getFullYear() - input_years
</script>

<template>
  <main>
    <span>Hello, <span class="name">{{name}}</span>!</span> 
    <template v-if="age == 1">
      <p>You are <span class="age">one</span> year old!</p>
    </template>
    <template v-else-if="age > 0">
      <p>You are <span class="age">{{age}}</span> years old!</p>
    </template>
    <template v-else>
      <p>Your age is a mystery!</p>
    </template>
  </main>
</template>

<style>
body {
  font-family: Helvetica, sans-serif;
  font-size: 1.2rem;
  font-weight: 600;
}

.name {
  color: firebrick;
  font-weight: 900;
}

.age {
  color: Navy;
  text-decoration: underline;
}
</style>
