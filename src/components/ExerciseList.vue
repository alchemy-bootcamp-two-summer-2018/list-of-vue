<template>
  <section>
    <h2>Your workout</h2>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
  </section>
</template>

<script>
import Exercise from './Exercise.vue';

export default {
  
  props: {
    exercises: Array,
    onRemove: Function
  },

  components: {
    Exercise,
  }

};
</script>

<style scoped>

section {
    margin: 10px 5%;
}
h2 {
    font-size: 36px;
}
ul {
  list-style: none;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}

</style>
