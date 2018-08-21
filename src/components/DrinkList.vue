<template>
  <div>
    <h3>Al's Favorite Cocktails</h3>
    <ul>
      <Drink v-for="drink in drinks"
        v-bind:key="drink.name"
        v-bind:drink="drink"
        v-bind:onRemove="onRemove"
      />
    </ul>
  </div>
    
</template>

<script>
import Drink from './Drink.vue';

export default {
  props: {
    drinks: Array,
    onRemove: Function
  },
  components: {
    Drink
  }

};
</script>


<style>
ul {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    list-style-type: none;
    margin: 0;
    padding: 0;
}

</style>
