<template>
  <div id="app">

    <ToDo></ToDo>
  </div>
</template>

<script>
import ToDo from "./components/ToDo";
export default {

  name: 'App',
  components: {
    ToDo


  }
}
</script>

<style>
#app {

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-family: "montserrat",sans-serif;
  font-size: 15px;
}
</style>
