<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ExerciseList from './components/ExerciseList';
import AddExerciseForm from './components/AddExerciseForm';

export default {
  name: 'app',
  components: {
    ExerciseList,
    AddExerciseForm,
  }

  
};
</script>

<style>



</style>
