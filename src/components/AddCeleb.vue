<template>
  <form v-on:submit.prevent="handleSubmit">
    <p>
      <label>
        Name: <input v-model="name" placeholder="Celeb Name">
      </label>
    </p>
    <p>
      <label>
        Role: <input v-model="role" placeholder="Celeb Role">
      </label>
    </p>
    <p>
      <label>
        Crew: <input v-model="crew" placeholder="Crew">
      </label>
    </p>
    <p>
      <button>Add Celeb</button>
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
      role: '',
      crew: ''
    };
  },
  methods: {
    handleSubmit() {
      const newCeleb = {
        name: this.name,
        role: this.role,
        crew: this.crew
      };
      this.onAdd(newCeleb);
      
      this.name = '';
      this.role = '';
      this.crew = '';
    }
  }
};
</script>

<style>
</style>
