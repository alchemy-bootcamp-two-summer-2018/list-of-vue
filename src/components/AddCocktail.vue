<template>
  <form v-on:submit.prevent="handleSubmit">
    <p>
      <label>
        Name: <input v-model="name" placeholder="Cocktail Name">
      </label>
    </p>
    <p>
      <label>
        Price: <input v-model="price" placeholder="Cocktail Price">
      </label>
    </p>
    <p>
      <label>
        Liquor: <input v-model="liquor" placeholder="Cocktail Liquor">
      </label>
    </p>
    <p>
      <button>Add Cocktail</button>
    </p>
  </form>
</template>

<script>
export default {
  props: {
    onAdd: Function
  },
  data() {
    return {
      name: '',
      price: '',
      liquor: ''
    };
  },
  methods: {
    handleSubmit() {
      const newCocktail = {
        name: this.name,
        price: this.price,
        liquor: this.liquor
      };
      this.onAdd(newCocktail);
      
      this.name = '';
      this.price = '';
      this.liquor = '';
    }
  }
};
</script>

<style>
</style>