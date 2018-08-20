<template>
    <div class="cute-animal-list">
        <h2>This is my Cute Animal List</h2>
        <ul>
            <CuteAnimal v-for="cuteAnimal in cuteAnimals"
                v-bind:key="cuteAnimal.name"
                v-bind:cuteAnimal="cuteAnimal"
            />
        </ul>
    </div>
</template>

<script>
import CuteAnimal from './CuteAnimal.vue';

export default {
    props: {
        cuteAnimals: Array
    },
    components: {
        CuteAnimal
    }
};
</script>