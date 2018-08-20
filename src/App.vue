<template>
  <div id="app">
    <h1>Hello Boozy World</h1>
    <DrinkList v-bind:drinks="drinks" v-bind:onRemove="handleRemove"/>
    <AddDrink v-bind:onAdd="handleAdd"/>
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
  },
  methods: {
    handleAdd(drink) {
      this.drinks.push(drink);
      console.log(this.drinks);
    },
    handleRemove(drink) {
      const index = this.drinks.indexOf(drink);
      if(index !== -1) {
        this.drinks.splice(index, 1);
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
