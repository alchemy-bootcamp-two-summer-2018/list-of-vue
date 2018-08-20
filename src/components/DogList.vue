<template>
  <div>
    <ul>
      <Dog v-for="dog in dogs"
      v-bind:key="dog.name"
      v-bind:dog="dog"
      v-bind:onRemove="onRemove"
      />
    </ul>
  </div>
</template>

<script>

import Dog from './Dog.vue';

export default {
  props: {
    dogs: Array,
    onRemove: Function
  },
  components: {
    Dog
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: block;
  margin: 0 10px;
}
</style>
