<template>
    <div class="animal">
        <div class="kitten" v-if="cuteAnimal.type === 'Kitten'">
            <h2>Kitten Alert!</h2>
            <h3>{{ cuteAnimal.name }} the Kitten</h3>
            <img v-bind:src="cuteAnimal.img">
            <button v-on:click="onRemove(cuteAnimal)">Remove this {{ cuteAnimal.type }}</button>
        </div>

        <div class="not-kitten" v-else>
            <h3>{{ cuteAnimal.name }} the {{ cuteAnimal.type }}</h3>
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

    .animal {
        border: 2px solid bisque;
        max-width: 500px;
        background-color: rgb(218, 214, 214);
        width: 100%;
    }

    .animal img {
        width: 200px;
        height: 200px;
        object-fit: cover;
    }

    .kitten h2 {
        background-color: bisque;
        color: white;
        padding: 10px;
        letter-spacing: 2px;
    }

    .animal h3 {
        padding: 20px;
        font-size: 24px;
    }

    .not-kitten {
         height: 100%;
    }

</style>