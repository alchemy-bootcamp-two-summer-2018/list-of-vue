<template>
    <section>
        <WhaleList v-bind:whales="whales"/>
        <AddWhale v-bind:onAdd="handleAdd"/>
    </section>
</template>

<script>
import WhaleList from './components/WhaleList.vue'
import whales from './whales.js'
import AddWhale from './components/AddWhale.vue'

export default {
    name: 'app',
    data() {
        return { whales };
    },
    components: {
        WhaleList,
        AddWhale
    },
    methods: {
        handleAdd(whale) {
            this.whales.push(whale);
        }
    }
}
</script>

<style>

</style>
