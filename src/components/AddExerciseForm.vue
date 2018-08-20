<template>
  <form>
    <label>
      Movement Name: <input v-model="name" placeholder="e.g. bench, squat, etc">
    </label>
  
    <label>
      Sets: <input placeholder="Enter a number">
    </label>
  
    <label>
      Reps: <input placeholder="Enter a number">
    </label>
    <button>Add Exercise</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      role: '',
      crew: ''
    };
  },
};
</script>

<style scoped>
label {
  display: block;
}
</style>
