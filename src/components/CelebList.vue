<template>
  <div>
    <h2>Celebs</h2>
    <ul>
      <Celeb v-for="celeb in celebs"
        v-bind:key="celeb.name"
        v-bind:celeb="celeb"
        v-bind:onRemove="onRemove"
      />
    </ul>
  </div>
</template>

<script>
import Celeb from './Celeb.vue';
export default {
  props: {
    celebs: Array,
    onRemove: Function
  },
  components: {
    Celeb
  }
};
</script>

<style>
</style>