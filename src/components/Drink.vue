<template>
  <li>
    <p>
      <img v-bind:src="drink.image">
      The {{ drink.name }} is a {{ drink.baseSpirit }}-based {{ drink.era }} cocktail from {{ drink.year }}.
    </p>
    <p v-if="drink.containsEgg === true">
      <em>*contains raw egg</em>
    </p>

    <p>
      <button v-on:click="onRemove(drink)">Remove this drink</button>
    </p>
  </li>    
</template>

<script>
export default {
  props: {
    drink: Object,
    onRemove: Function
  }
};
</script>

<style>

</style>
