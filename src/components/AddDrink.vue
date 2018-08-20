<template>
  <form v-on:submit.prevent="handleSubmit">
    <h3>Add a Drink</h3>
    <p>
      <label>
        Cocktail Name: <input v-model="name" placeholder="Name">
      </label>
    </p>
    <p>
      <label>
        Base Spirit: <input v-model="baseSpirit" placeholder="Spirit">
      </label>
    </p>
    <p>
      <label>
        Year Created: <input v-model="year" placeholder="Year">
      </label>
    </p>
    <p>
      <label>
        Era: <input v-model="era" placeholder="Era">
      </label>
    </p>
    <p>
      <label>
        Does it contain raw egg? <input type="radio" v-model="containsEgg"> Yes <input type="radio" v-model="containsEgg"> No
      </label>
    </p>
    <p>
      <button>Add Drink</button>
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
      baseSpirit: '',
      year: '',
      era: '',
      containsEgg: ''
    };
  },
  methods: {
    handleSubmit() {
      const newDrink = {
        name: this.name,
        baseSpirit: this.baseSpirit,
        year: this.year,
        era: this.era,
        containsEgg: this.containsEgg
      };
      this.onAdd(newDrink);

      this.name = '';
      this.baseSpirit = '';
      this.year = '';
      this.era = '';
      this.containsEgg = '';
    }
  }
};
</script>

<style>

</style>
