<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <h1>All The Dogs</h1>
    <DogList v-bind:dogs="dogs"/>
    <AddDog/>
  </div>
</template>

<script>
import DogList from './components/DogList.vue';
import AddDog from './components/AddDog.vue';
import dogs from './dogs.js';

export default {
  name: 'app',
  data() {
    return { dogs };
  },
  components: {
    DogList,
    AddDog
  }
};
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
