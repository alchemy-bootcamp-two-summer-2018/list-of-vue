<template>
  <li>
    <p>
      <img class="drink-image" v-bind:src="drink.image">
    </p>
    <p>  
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
.drink-image {
  height: 300px;
  width: 300px;
}
li {
  max-width: 33%;
  min-width: 30%;
}

</style>
