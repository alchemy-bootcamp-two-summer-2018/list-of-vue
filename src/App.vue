<template>
  <div id="app">
    <h1>Workout Tracker</h1>
    <img alt="workout logo" src="./assets/logo.png">
    <AddExerciseForm/>
    <ExerciseList/>
  </div>
</template>

<script>
import ExerciseList from './components/ExerciseList';
import AddExerciseForm from './components/AddExerciseForm';
import workout from './workout.js';

export default {
  name: 'app',
  components: {
    ExerciseList,
    AddExerciseForm,
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
