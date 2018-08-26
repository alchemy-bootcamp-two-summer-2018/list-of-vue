<template>
    <form v-on:submit.prevent="handleSubmit">
        <h2>Add a whale!</h2>
        <p>
            <label>
                Species: <input v-model="species" placeholder="Name of Species">
            </label>
        </p>
        <p>
            <label>
                Weight: <input v-model="weight" placeholder="Average Weight">
            </label>
        </p>
        <p>
            <label>
                URL: <input v-model="url" placeholder="Insert URL Here">
            </label>
        </p>
        <p>
            <button>Submit</button>
        </p>
    </form>
</template>

<script>
export default {
    props: {
        onAdd: Function
    },
    data() {
        return {
            species: '',
            weight: '',
            url: ''
        };
    },
    methods: {
        handleSubmit() {
            const newWhale = {
                species: this.species,
                weight: this.weight,
                url: this.url
            };
        this.onAdd(newWhale);

        this.species = '';
        this.weight = '';
        this.url = '';
        }
    }
};
</script>

<style>

</style>
