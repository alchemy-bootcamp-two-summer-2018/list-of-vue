<template>
    <div>
        
        <ul class="flex-container">
         <Cat v-for="cat in cats"
            v-bind:key="cat.name"
            v-bind:cat="cat"
            v-bind:onRemove="onRemove"
            />
        </ul>
    </div>
</template>

<script>
import Cat from './cat.vue';

export default {
  props: {
    cats: Array,
    onRemove: Function
  },
  components: {
    Cat
  }

};
</script>

<style scoped>

.flex-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-items: space-evenly;
  max-width: 900px;
} 


</style>
