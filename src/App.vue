<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CuteAnimalForm msg="This is a test"/>
  </div>
</template>

<script>
import CuteAnimalForm from './components/CuteAnimalForm.vue';
// import cuteAnimals from './cute-animals.js';

export default {
  name: 'app',
  components: {
    CuteAnimalForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
