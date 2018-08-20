<template>
  <form v-on:submit.prevent="handleSubmit">
    <p>
      <label>
        Name: <input v-model="name" placeholder="Dogo Name">
      </label>
    </p>
    <p>
      <label>
        Type: <input v-model="type" placeholder="Dogo Type">
      </label>
    </p>
    <p>
      <label>
        Food: <input v-model="food" placeholder="Favorite Food">
      </label>
    </p>
    <p>
      <button>Add A Dogo</button>
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
      type: '',
      food: ''
    };
  },
  methods: {
    handleSubmit() {
      const newDogo = {
        name: this.name,
        type: this.type,
        food: this.food
      };
      this.onAdd(newDogo);
      
      this.name = '';
      this.type = '';
      this.food = '';
    }
  }
};
</script>

<style>

</style>
