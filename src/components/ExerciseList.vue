<template>
  <section>
    <h2>Your workout</h2>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
      />
    </ul>
  </section>
</template>

<script>
import Exercise from './Exercise.vue';

export default {
  
  props: {
    exercises: Array,
  },

  components: {
    Exercise,
  }

};
</script>

<style scoped>

h2 {
    font-size: 36px;
}
</style>
