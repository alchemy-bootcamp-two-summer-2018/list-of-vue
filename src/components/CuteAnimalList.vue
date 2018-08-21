<template>
    <div class="cute-animal-list">
        <h2>Cute Animal List</h2>
        <CuteAnimal v-for="cuteAnimal in cuteAnimals"
            v-bind:key="cuteAnimal.name"
            v-bind:cuteAnimal="cuteAnimal"
            v-bind:onRemove="onRemove"
        />
    </div>
</template>

<script>
import CuteAnimal from './CuteAnimal.vue';

export default {
    props: {
        cuteAnimals: Array,
        onRemove: Function
    },
    components: {
        CuteAnimal
    }
};
</script>