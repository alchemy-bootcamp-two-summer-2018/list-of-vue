<template>
    <li>
        <h3 v-bind:class="{ MeeGorengMamak: dish.name === 'Mee Goreng Mamak' }">{{ dish.name}}</h3>
        <p v-if="dish.name === 'Mee Goreng Mamak'">
            <strong>{{dish.name}} is Singapore's favorite noodle</strong>
        </p>
        <p v-else>{{dish.name}} is a {{dish.ethnicOrigin}} dish</p>
        <p>Spice level is {{dish.spiceLevel}}</p>
        <img class="dishImages" v-bind:src="dish.image"/>
        <p>
            <button v-on:click="onRemove(dish)">remove this dish</button>
        </p>
    </li>
</template>    

<script>
export default {
  props: {
    dish: Object,
    onRemove: Function
  }
};
</script>

<style>
.dishImages {
    width:300px;}

</style>
