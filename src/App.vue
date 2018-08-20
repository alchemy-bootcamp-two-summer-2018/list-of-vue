<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
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

<style>

img {
  width: 300px;
}


</style>
