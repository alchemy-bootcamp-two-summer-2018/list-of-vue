<template>
  <div id="app">
    <h1>Workout Tracker</h1>
    <img alt="workout logo" src="./assets/logo.png">
    <AddExerciseForm />
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
