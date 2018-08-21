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
          <button>Add Cute Animal</button>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
