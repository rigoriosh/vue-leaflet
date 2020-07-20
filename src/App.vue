<template>
  <div id="app" class="cotainer-fluid">    
    <Brew msg="Welcome to Map App"/>
  </div>
</template>

<script>
import Brew from './components/Brew.vue'

export default {
  name: 'App',
  components: {
    Brew
  }
}
</script>

<style>
body{
  background: black;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rebeccapurple;
  margin-top: 60px;
  background: #2c3e50;
}
</style>
