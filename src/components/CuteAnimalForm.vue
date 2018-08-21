<template>
  <div class="cute-animal-form">
    <h1>Add a Cute Animal</h1>
    <form v-on:submit.prevent="handleSubmit">
        <p>
            <label>
                Name: <input v-model="name" placeholder="Animal Name">
            </label>
        </p>
        <p>
            <label>
                Type: <input v-model="type" placeholder="Animal Type">
            </label>
        </p>
        <p>
            <label>
                Image: <input v-model="img" placeholder="Image URL">
            </label>
        </p>
        <p>
          <button>Add</button>
        </p>
    </form>
  </div>
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
      img: ''
    }
  },

  methods: {
    handleSubmit() {
      const newCuteAnimal = {
        name: this.name,
        type: this.type,
        img: this.img
      };
      this.onAdd(newCuteAnimal);
        this.name = '',
        this.type = '',
        this.img = ''
    }
  }
};
</script>

<style scoped>
  input {
    padding: 5px;
  }

  p {
    padding: 10px;
  }

  h1 {
    padding: 10px 10px 20px 10px;
  }
</style>
