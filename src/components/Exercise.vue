<template>
  <li>
    <h3>Movement Name: {{ exercise.name }}</h3>
    <p>Sets: {{ exercise.sets }}</p>
    <p>Reps: {{ exercise.reps }}</p>
    <p>Notes: {{ exercise.notes }} </p>
    <button>Remove this movement</button>
  </li>
</template>

<script>
export default {
  props: {
    exercise: Object,
  }

};
</script>

<style scoped>

button {
  padding: 4px 8px;
  cursor: pointer;
}

</style>
