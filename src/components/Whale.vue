<template>
    <li>
        <h3 v-bind:class="{ bluewhale: whale.species === 'Blue Whale' }"> {{ whale.species }} 
            <span v-if="whale.species === 'Blue Whale'">
            <strong class="alert">**Big Whale Alert!**</strong>
        </span></h3>
        <img v-bind:src="whale.url">

    </li>
</template>

<script>
export default {
    props: {
        whale: Object
    }
}
</script>

<style scoped>
.alert {
    color: red;
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    padding-left: 3%;
}

</style>

