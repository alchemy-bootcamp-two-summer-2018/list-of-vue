<template>
  <section>
    <h2>Your workout</h2>
    <h3>Upper Body</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'upper'"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
    <h3>Lower Body</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'lower'"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
    <h3>Core</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'core'"
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

* {
    color: navy;
}

section {
    margin: 10px 5%;
}
h2 {
    font-size: 48px;
}
h3 {
    font-size: 32px;
    border-bottom: 1px solid navy;
}
ul {
  list-style: none;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
}

</style>
