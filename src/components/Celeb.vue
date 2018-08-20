<template>
  <li>
      <h3 v-bind:class="{ captain: celeb.role === 'captain' }">{{ celeb.name }}</h3>
      <p v-if="celeb.role === 'captain'">
        <strong>Captain of the {{ celeb.crew}}</strong>
      </p>
      <p v-else>{{ celeb.role }} of {{ celeb.crew }}</p>

      <p>
        <button v-on:click="onRemove(celeb)">remove this celeb</button>
      </p>
  </li>
</template>

<script>
export default {
  props: {
    celeb: Object,
    onRemove: Function
  }
};
</script>

<style scoped>
</style>