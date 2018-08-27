<template>
  <li>
      <h3 v-bind:class="{ $10: cocktail.price === '$10' }">{{ cocktail.name }}</h3>
      <p v-if="cocktail.price === '$10'">
        <strong>Cocktail Price {{ cocktail.price}}</strong>
      </p>
     
    {{cocktail.name}}
    {{cocktail.price}}
    {{cocktail.liquor}}
  </li>
</template>

<script>
export default {
  name: 'Cocktail',
  props: {
    cocktail: Object,
  }
};

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>