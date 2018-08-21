<template>
  <div id="app">
    <Header/>
    <h2>Your Workout</h2>
    <AddExerciseForm 
      v-bind:onAdd="handleAdd" 
    />
    <ExerciseList 
      v-bind:exercises="exercises" 
      v-bind:onRemove="handleRemove"
    />

    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';

import AddExerciseForm from './components/AddExerciseForm';
import ExerciseList from './components/ExerciseList';
import exercises from './exercises.js';

export default {
  name: 'app',
  data() {
    return { exercises };
  },
  components: {
    AddExerciseForm,
    ExerciseList,
    Header,
    Footer
  },
  methods: {
    handleAdd(exercise) {
      this.exercises.push(exercise);
    },
    handleRemove(exercise) {
      const index = this.exercises.indexOf(exercise);
      if(index !== -1) {
        this.exercises.splice(index, 1);
      }
    }

  }


};
</script>

<style scoped>
* {
    color: rgb(0, 0, 68);
}
h2 {
  margin-top: 16px;
  font-size: 52px;
}



</style>
