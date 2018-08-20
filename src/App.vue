<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <h1>All The Dogos</h1>
    <AddDog v-bind:onAdd="handleAdd"/>
    <DogList v-bind:dogs="dogs" v-bind:onRemove="handleRemove"/>
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
  },
  methods: {
    handleAdd(dog) {
      this.dogs.push(dog);
    },
    handleRemove(dog) {
      const index = this.dogs.indexOf(dog);
      if(index !== -1) {
        this.dogs.splice(index, 1);
      }
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
