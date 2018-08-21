<template>
    <div class="cute-animal-list">
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

<style scoped>

    .cute-animal-list {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 2fr));
        grid-gap: 20px;
        margin: 20px;
    }

</style>