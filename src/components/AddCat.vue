<template>
<section class="form">
  <form v-on:submit.prevent="handleSubmit">
  <p> 
  <input v-model="name" placeholder="Your Cats Name">
  </p>
  <p> 
  <input v-model="breed" placeholder="Your Cats Breed">
  </p>
  <p> 
  <input v-model="hobby" placeholder="Your Cats Favorite Hobby">
  </p>
  <p> 
  <input v-model="img" placeholder="Paste Your Cats Image URL Here" >
  </p>
  <p> 
    <input v-model="age" placeholder="Add Your Cats Age Here" >
  </p>
  <p>
  <button> Add Your Precious Cat</button>
  </p>
</form>
</section>
</template>

<script>
export default {
  props: {
    onAdd: Function
  },
  data(){
    return {
      name: '',
      breed:'',
      hobby:'',
      img:'',
      age:'',
    };
  },
  methods: {
    handleSubmit() {
      const newCat = {
        name: this.name,
        breed: this.breed,
        hobby: this.hobby,
        img: this.img,
        age: this.age
      };

      this.onAdd(newCat);

      this.name = '';
      this.breed = '';
      this.hobby = '';
      this.img = '';
      this.age = '';
    }
  }
};

</script>

<style scoped>

button {
  background-color: #7669e7;
    width: 300px;
    padding: 20px;
    color: white;
    font-size: 18px;
    border-bottom: solid 5px #27b0e4;
    border-radius: 100px;
}
.form {
  background-color: white;
  height: 450px;
  padding: 20px;
  position: sticky;
  top: 0;
}


</style>
