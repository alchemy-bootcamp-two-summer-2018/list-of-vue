<template>
  <div id="app">
    <img alt="workout logo" src="./assets/logo.png">
    <AddExerciseForm/>>
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

img {
  width: 300px;
}

</style>
