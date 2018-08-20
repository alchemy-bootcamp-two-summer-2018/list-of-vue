<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <CuteAnimalForm v-bind:onAdd="handleAdd" v-bind:cuteAnimals="cuteAnimals"/>
    <CuteAnimalList v-bind:cuteAnimals="cuteAnimals"/>
  </div>
</template>

<script>
import CuteAnimalForm from './components/CuteAnimalForm.vue';
import cuteAnimals from './cute-animals.js';
import CuteAnimalList from './components/CuteAnimalList.vue';

export default {
  name: 'app',
  data() {
    return { cuteAnimals };
  },
  components: {
    CuteAnimalForm,
    CuteAnimalList
  },
  methods: {
    handleAdd(cuteAnimal) {
      this.cuteAnimals.push(cuteAnimal);
    }
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
