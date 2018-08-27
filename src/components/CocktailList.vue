<template>
  <div class="hello">
    <h2>Menu</h2>
    <ul>
      <Cocktail v-for="cocktail in cocktails"
        v-bind:key="cocktail.name"
        v-bind:cocktail="cocktail"
      />
    </ul>
  </div>
</template>

<script>
import Cocktail from './Cocktail.vue';

export default {
  name: 'CocktailList',
  props: {
    cocktails: Array,
   
  },
  components: {
  Cocktail
  }
};

</script>