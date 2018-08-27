<template>
    <div class="foodlist">
        <p>Singapore is a diverse city full of food that reflects its diverse culture. Below you will find a list of delicious Singaporean food!</p>
        <br>
        <h2>List of Singapore's popular food</h2>
        <ul>
            <Dish v-for="dish in dishes"
            v-bind:key="dish.name"
            v-bind:dish="dish"
            v-bind:onRemove="onRemove"/>
        </ul>
        <br>
    </div>
</template>

<script>
import Dish from './Dish.vue';

export default {
  props: {
    dishes: Array,
    onRemove: Function
  },
  components: {
    Dish
  }
};

</script>

<style>

.foodlist {
  color: #2B3D41;
  font-family: 'Josefin Sans', sans-serif;
}

</style>

