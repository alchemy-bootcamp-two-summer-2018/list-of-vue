<template>
<section class="form">
  <div class="form-title">
    <img class="kitty-logo" src="kittlogo.png">
    <h1> Cat Fancy Talent Show </h1>
    <p> If you think you have the custest cat in town sign up and show up on your cat's 
      performance date!</p>
  </div>

  <form v-on:submit.prevent="handleSubmit">
  <p> 
  <input v-model="name" placeholder="Your Cats Name" required>
  </p>
  <p> 
  <input v-model="breed" placeholder="Your Cats Breed" required>
  </p>
  <p> 
  <input v-model="hobby" placeholder="Your Cats Favorite Hobby" required>
  </p>
  <p> 
  <input v-model="img" placeholder="Paste Your Cats Image URL Here" required >
  </p>
  <p> 
    <input v-model="age" placeholder="Add Your Cats Age Here" required >
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

.kitty-logo {
  width: 150px;
}

button {
  background-color: #7669e7;
  width: 100%;
  padding: 20px;
  color: white;
  font-size: 18px;
  border-bottom: solid 5px #27b0e4;
  border-radius: 100px;
}
.form {
  background-color: white;
  max-width: 400px;
  height: 700px;
  padding: 20px;
  position: sticky;
  top: 50px;
   box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  transition: all 0.3s cubic-bezier(.25,.8,.25,1);
}

.form:hover {
  box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
}
.form-title {
  padding: 15px;
  text-align: center;
}


</style>
