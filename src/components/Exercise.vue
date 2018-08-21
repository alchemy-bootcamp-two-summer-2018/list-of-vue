<template>
  <li>
    <h3>Movement Name: {{ exercise.name }}</h3>
    <p>Type: {{ exercise.type }}</p>
    <p>Sets: {{ exercise.sets }}</p>
    <p>Reps: {{ exercise.reps }}</p>
    <p>Notes: {{ exercise.notes }} </p>
    <!-- <p 
      v-if="exercise.name.toLowerCase() !== 'squat'" style="color: red;">
      don't skip leg day
    </p>
    <p v-else
      style="color: blue;">
      do you even lift?
    </p> -->
    <button
      v-on:click="onRemove(exercise)">
      Remove this exercise
    </button>
  </li>
</template>

<script>
export default {
  props: {
    exercise: Object,
    onRemove: Function
  }

};
</script>

<style scoped>

* {
    color: navy;
}

li {
    max-width: 300px;
    margin: 15px 25px;
    border: 1px solid navy;
    border-radius: 5px;
    box-shadow: 0 2px 4px 0 rgba(0,0,0,0.5);
    display: flex;
    flex-direction: column;
    justify-self: center;
}

h3 {
  padding: 10px;
}

p {
  padding: 1px;
}

button {
  padding: 4px 8px;
  margin: 0px;
  margin-top: 6px;
  cursor: pointer;
  background-color: navy;
  color: white;
}


</style>
