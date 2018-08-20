<template>
  <li>
    <h3>{{ dog.name }}</h3>
    <img v-bind:src="dog.img">
    <p v-if="dog.type === 'Cartoon Dogo'"
      v-bind:class="{ cartoon: dog.type === 'Cartoon Dogo' }"
    >
      <strong>This Dogo is a <em>Cartoon</em> Dogo</strong>
    </p>
    <p v-else>{{ dog.type }}</p>
    <p>{{ dog.food }}</p>

    <p>
      <button v-on:click="onRemove(dog)">Remove</button>
    </p>
  </li>
</template>

<script>
export default {
  props: {
    dog: Object,
    onRemove: Function
  }
};
</script>

<style scoped>
.cartoon {
  color: steelblue;
}
img {
  width: 100px;
}
</style>
