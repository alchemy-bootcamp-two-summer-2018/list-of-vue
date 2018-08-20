<template>
  <div>
    <h3>Al's Favorite Cocktails</h3>
    <ul>
      <Drink v-for="drink in drinks"
        v-bind:key="drink.name"
        v-bind:drink="drink"
      />
    </ul>
  </div>
    
</template>

<script>
import Drink from './Drink.vue';

export default {
  props: {
    drinks: Array
  },
  components: {
    Drink
  }

};
</script>

<style>

</style>
