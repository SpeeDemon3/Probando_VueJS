<script setup lang="ts">
    defineProps<{
        name: string,
        lastName: string
    }>()

</script>

<template>
    <div class="greetings">
      <h3 class="green">Hola {{ name }} {{ lastName }}</h3>
    </div>
  </template>
  
  <style scoped>
  h1 {
    font-weight: 500;
    font-size: 2.6rem;
    position: relative;
    top: -10px;
  }
  
  h3 {
    font-size: 1.2rem;
  }
  
  button {
    background-color: #6acf6a;
  }
  
  .greetings h1,
  .greetings h3 {
    text-align: center;
  }
  
  @media (min-width: 1024px) {
    .greetings h1,
    .greetings h3 {
      text-align: left;
    }
  }
  </style>