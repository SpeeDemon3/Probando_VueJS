<script setup lang="ts">
import { reactive, ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import ComponentProp from './components/ComponentProp.vue'
import ComponentEmit from './components/ComponentEmit.vue'
import './assets/main.css'


let count = ref(0);

let name = ref("Arya");

let nameUser = ref("Antonio");
let nameBrother = ref("Sonia");

const list = ref(["perro", "gato", "aguila", "león", "ballena"]);

const obj = reactive({
  marca : "seat",
  modelo : "leon",
  km : 12.321
})


</script>

<template>

  <body :class ="{black: count >= 50}">

    <h1>Bienvenido/a {{name}}</h1>

    <header :class = "{darkgreen: count >= 5}">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="Antonio Ruiz" />
    </div>

    <div>

      <h3 v-if = 'nameUser === "Luis"'>Hola {{ nameUser }}</h3>
      <h3 v-else-if = 'nameBrother === "Pepe"'>Hola {{ nameBrother }}</h3>
      <h3 v-else>Hola usuario no logeado</h3>

      <ul>

        <li v-for="item in list" :key="item">
          {{item}}
        </li>
      
      </ul>

      <ul>
        <li v-for="(item, index) in list" :key="index">
          {{ `${index} - ${item}` }}       
         </li>
      </ul>

      <ul>
        <li v-for="(item, index) in obj" :key="index">
          {{ `${index} : ${item}` }}
        </li>
      </ul>

    </div>

  </header>

  <button @click="count++">Count: {{ count }}</button>

  <div>
    <ComponentProp name="Patricia" lastName="Luengo Cuesta"/>
  </div>

  <div>
    <ComponentEmit @eventoEmit="count++"/>
  </div>

  </body>

</template>

<style scoped>

button {
  height: 2em;
  width: 10em;
  border: none;
  margin-top: 4em;
  margin-left: 20em;
}

.black {
  background-color: black;
}

.darkgreen {
  background-color: #173102;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
