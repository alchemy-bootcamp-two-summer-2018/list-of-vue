<template>
  <section>
    <img alt="Vue logo" src="./assets/logo.png">
    <p>some random content</p>
    <AddCocktail v-bind:onAdd="handleAdd"/>
    <CocktailList v-bind:cocktails="cocktails"/>
  </section>
</template>

<script>
import CocktailList from './components/CocktailList.vue';
import AddCocktail from './components/AddCocktail.vue';
import cocktails from './cocktails';

export default {
  name: 'app',
  data() {
    return { cocktails };
  },
  components: {
    AddCocktail,
    CocktailList
  },
  methods: {
    handleAdd(cocktail) {
      this.cocktails.push(cocktail);
    },
    handleRemove(cocktail) {
      const index = this.cocktail.indexOf(cocktail);
      if(index !== -1) {
        this.cocktails.splice(index, 1);
      }
    }
  }
};
</script>

<style scoped>

section {
  margin-top: 60px;
}
p {
  color: steelblue;
}
</style>
