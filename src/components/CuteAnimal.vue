<template>
    <li>
        <h3>Meet {{ cuteAnimal.name }} the {{ cuteAnimal.type }}</h3>
        <img v-bind:src="cuteAnimal.img">
    </li>
</template>

<script>
export default {
    props: {
        cuteAnimal: Object,
    }
};
</script>