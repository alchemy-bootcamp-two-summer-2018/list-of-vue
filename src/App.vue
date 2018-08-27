<template>
  <section class='content'>
    <img alt="hawker center" src="./assets/hawker.jpg">
    <h1>Welcome to the streets of Singapore!</h1>
    <DishList v-bind:dishes="dishes" v-bind:onRemove="handleRemove"/>
    <p class='question'>Do you have a favorite Singapore dish that you would like to add to this list? You can below!</p>
    <AddDish v-bind:onAdd="handleAdd"/>
  </section>
</template>
<script>
import DishList from './components/DishList.vue';
import AddDish from './components/AddDish.vue';
import dishes from './dishes';
export default {
  name: 'app',
  data() {
    return { dishes };
  },
  components: {
    AddDish,
    DishList
  },
  methods: {
    handleAdd(dish) {
      this.dishes.push(dish);
    },
    handleRemove(dish) {
      const index = this.dishes.indexOf(dish);
      if(index !== -1) {
        this.dishes.splice(index, 1);
      }
    }
  }
};
</script>
 <style>
h1 {
  font-family: 'Josefin Sans', sans-serif;
  color: red;
  font-size: 30px;
}
.content {
  text-align:center;
}
.question {
  color:red;
  font-weight:bold;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
