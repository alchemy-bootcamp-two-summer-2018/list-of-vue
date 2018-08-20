<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import DrinkList from './components/DrinkList.vue';
import AddDrink from './components/AddDrink.vue';
import drinks from './drinks';

export default {
  name: 'app',
  data() {
    return { drinks };
  },
  components: {
    AddDrink,
    DrinkList
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
