<template>
  <div id="app">
    <h1>Workout Tracker</h1>
    <img alt="workout logo" src="./assets/logo.png">
    <AddExerciseForm v-bind:onAdd="handleAdd" />
    <ExerciseList v-bind:exercises="exercises" />
  </div>
</template>

<script>
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
  },
  methods: {
    handleAdd(exercise) {
      this.exercises.push(exercise);
    }

  }


};
</script>

<style scoped>

h1 {
  font-size: 72px;
  font-weight: 500;
}

img {
  width: 300px;
}

</style>
