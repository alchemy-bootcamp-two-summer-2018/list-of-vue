<template>
    <div class="animal">
        <h2 v-if="cuteAnimal.type === 'Kitten'">Kitten Alert!</h2>
        <h3>{{ cuteAnimal.name }} the {{ cuteAnimal.type }}</h3>
        <img v-bind:src="cuteAnimal.img">
        <button v-on:click="onRemove(cuteAnimal)">Remove this {{ cuteAnimal.type }}</button>
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

    * { box-sizing: border-box; }

    .animal button {
        margin: 20px auto;
    }

    .animal {
        border: 2px solid bisque;
        max-width: 500px;
        background-color: rgb(218, 214, 214);
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .animal img {
        width: 200px;
        height: 200px;
        object-fit: cover;
    }

    .animal h2 {
        background-color: bisque;
        color: white;
        padding: 10px;
        letter-spacing: 2px;
        width: 100%;
    }

    .animal h3 {
        padding: 20px;
        font-size: 24px;
    }

    .not-kitten {
         height: 100%;
    }

</style>