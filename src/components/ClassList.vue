<template>
    <div>
        <br>
        <h2>CLASS COMPADRES</h2>
        <ol class="list-group">
            <Person v-for="person in persons"
                v-bind:key="person.name"
                v-bind:person="person"
                v-bind:onRemove="onRemove"
            />

        </ol>
    </div>
</template>

<script>
import Person from './Person.vue';

export default {
  props: {
    persons: Array,
    onRemove: Function
  },
  components: {
    Person
  }
};
</script>

<style>

</style>
