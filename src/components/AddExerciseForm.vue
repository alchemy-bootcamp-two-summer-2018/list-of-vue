<template>
  <section>
    <h2>Add a new exercise</h2>
    <form v-on:submit.prevent="handleSubmit">
      <label>
        Movement Name: <input v-model="name" placeholder="e.g. bench, squat, etc">
      </label>
    
      <label>
        Sets: <input v-model="sets" placeholder="Enter a number">
      </label>
    
      <label>
        Reps: <input v-model="reps" placeholder="Enter a number">
      </label>

      <label>
        Notes: <input v-model="notes" placeholder="Any thoughts?">
      </label>
      <button>Add Exercise</button>
    </form>
  </section>
</template>

<script>
export default {
  props: {
    onAdd: Function
  },

  data() {
    return {
      name: '',
      sets: '',
      reps: '',
      notes: ''
    };
  },

  methods: {
    handleSubmit() {
      const newExercise = {
        name: this.name,
        sets: this.sets,
        reps: this.reps,
        notes: this.notes
      };
      this.onAdd(newExercise);
      
      this.name = '';
      this.sets = '';
      this.reps = '';
      this.notes = '';

    }
  }  
};
</script>

<style scoped>

label {
  display: block;
}
h2 {
    font-size: 36px;
}
button {
  padding: 10px 15px;
  cursor: pointer;
}


</style>
