<template>
  <div class="hello">
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>