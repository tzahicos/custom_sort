<template>
  <div id="app">
    <sorted/>
  </div>
</template>

<script>
import Sorted from './components/Sorted'
export default {
  name: 'App',
  components: {
    Sorted
  }
}
</script>

<style>
body{
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
    height: 100%;
  width: 100%;
  position: fixed;
  z-index: 1;
  background-color: aqua;
}
</style>
