<template>
  <section>
    <h2>Add a new exercise</h2>
    <form v-on:submit.prevent="handleSubmit">
      <p>
        Movement Name: 
      </p>
      <input v-model="name" placeholder="e.g. bench, squat, etc" required>

      <p>
        Type:
      </p>
      <select v-model="type" required>
        <option disabled value="">Please select one</option>
        <option value="upper">Upper</option>
        <option value="lower">Lower</option>
        <option value="core">Core</option>
      </select>
    
      <p>
        Sets: 
      </p>
      <input v-model="sets" placeholder="Enter a number" required>
    
      <p>
        Reps: 
      </p>
      <input v-model="reps" placeholder="Enter a number" required>

      <p>
        Notes: 
      </p>
      <textarea v-model="notes" placeholder="Any thoughts?"></textarea>
    
      <button style="grid-column-start: span 2;">Add Exercise</button>
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
      type: '',
      sets: '',
      reps: '',
      notes: ''
    };
  },

  methods: {
    handleSubmit() {
      const newExercise = {
        name: this.name,
        type: this.type,
        sets: this.sets,
        reps: this.reps,
        notes: this.notes
      };
      this.onAdd(newExercise);
      
      this.name = '';
      this.type = '';
      this.sets = '';
      this.reps = '';
      this.notes = '';

    }
  }  
};
</script>

<style scoped>

* {
    color: navy;
}

section {
  margin: 25px 25%;

}
h2 {
    font-size: 36px;
}
form {
  display: grid;
  grid-template-columns: auto auto;
  border: 1px solid navy;
  border-radius: 5px;
  box-shadow: 0 2px 4px 0 rgba(0,0,0,0.5);
}

p, input, select, textarea {
  margin: 6px;
}

p {
  justify-self: end;
}
input, select, textarea {
  /* margin: 0px 10px; */
  border: 1px solid navy;
  padding: 3px;
}


button {
  padding: 10px 15px;
  cursor: pointer;
  background-color: navy;
  color: white;
}


</style>
