<template>
  <li>
    <h3>{{ dog.name }}</h3>
    <p>{{ dog.type }}</p>
    <p>{{ dog.color }}</p>
  </li>
</template>

<script>
export default {
  props: {
    dog: Object,
  }
};
</script>

<style scoped>

</style>
