<template>
  <div id="app">
  <h1>The Rick and Morty API</h1>
   
   <rickAndMorty/>
  </div>
</template>

<script>

import rickAndMorty from "./components/rickAndMorty.vue"

export default {
  name: 'App',
  components:{
    rickAndMorty
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin: 0px;

}

body{
margin: 0px;
padding: 0px;
}
h1{
  color:  rgb(60, 62, 68); 
  margin-left: 0px;
}
</style>
