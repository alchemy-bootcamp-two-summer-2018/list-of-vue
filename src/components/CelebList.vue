<template>
  <div class="celeb-list">
    <div class="welcome-text">Here are our celebrity members</div>
    <div class="racist-warning"> Note: Racist celebrities are in red </div>
      <Celeb v-for="celeb in celebs"
        v-bind:key="celeb.name"
        v-bind:celeb="celeb"
        v-bind:onRemove="onRemove"
      />
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