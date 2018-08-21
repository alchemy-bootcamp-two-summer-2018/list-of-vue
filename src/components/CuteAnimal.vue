<template>
    <div class="animal">
        <div class="kitten" v-if="cuteAnimal.type === 'Kitten'">
            <h2>Kitten Alert!</h2>
            <h3>Meet {{ cuteAnimal.name }}</h3>
            <img v-bind:src="cuteAnimal.img">
            <button v-on:click="onRemove(cuteAnimal)">Remove this {{ cuteAnimal.type }}</button>
        </div>

        <div class="not-kitten" v-else>
            <h3>Meet {{ cuteAnimal.name }} the {{ cuteAnimal.type }}</h3>
            <img v-bind:src="cuteAnimal.img">
            <button v-on:click="onRemove(cuteAnimal)">Remove this {{ cuteAnimal.type }}</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        cuteAnimal: Object,
        onRemove: Function
    }
};
</script>

<style scoped>

    .animal button {
        margin: 20px auto;
    }

    .animal div {
        padding-bottom: 15px
    }

    .animal {
        border: 2px solid bisque;
        max-width: 500px;
        margin: 50px auto;
        background-color: rgb(218, 214, 214);
    }

    .animal img {
        width: 80%
    }

    .kitten h2 {
        background-color: rgb(197, 67, 57);
        color: white;
        padding: 10px;
        letter-spacing: 2px;
    }

    .animal h3 {
        padding: 20px;
        font-size: 24px;
    }

</style>