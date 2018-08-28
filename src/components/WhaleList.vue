<template>
    <div>
        <h2>Whales are amazing.</h2>
        <ul class="whale-list">
            <Whale v-for="whale in whales"
            v-bind:key="whale.species"
            v-bind:whale="whale"/>
        </ul>
    </div>
</template>

<script>

import Whale from './Whale.vue'

export default {
    props: {
        whales: Array
    },

    components: {
        Whale
    }

}
</script>

<style scoped>


</style>
