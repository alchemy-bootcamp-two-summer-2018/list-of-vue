<template>
    <form v-on:submit.prevent="handleSubmit">
        <p>
            <label>
                Name: <input v-model="name">
            </label>
        </p>
        <p>
            <label>
                Ethnic-Origin: <input v-model="ethnicOrigin">
            </label>
        </p>
        <p>
            <label>
                Spice-Level: <input v-model="spiceLevel">
            </label>
        </p>
        <p>
            <label>
                Image: <input v-model="image" placeholder="imageUrl">
            </label>
        </p>
        <p>
        <button>Add Dish</button>
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
      name:'',
      ethnicOrigin: '',
      spiceLevel: '',
      image: ''
    };
  },
  methods: {
    handleSubmit() {
      const newDish = {
        name: this.name,
        ethnicOrigin: this.ethnicOrigin,
        spiceLevel: this.spiceLevel,
        image: this.image
      };
      this.onAdd(newDish);

      this.name = '';
      this.ethnicOrigin = '';
      this.spiceLevel = '';
      this.image = '';
    }
  }
};
</script>

<style>
</style>
