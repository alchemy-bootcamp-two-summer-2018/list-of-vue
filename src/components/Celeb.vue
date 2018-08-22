<template>
    <div class="bio" v-bind:class="{ racist: celeb.celebStatus === 'Famous for being racist' }">
        <h3 v-if="celeb.celebStatus === 'Famous for being racist'" > Ewwwwww </h3>
        <h3> <span class="celeb-prop"> Celebrity Name: </span> {{celeb.name}} </h3>
        <p> <span class="celeb-prop"> Celebrity Status: </span> {{celeb.celebStatus}} </p>
        <p> <span class="celeb-prop"> Fertility: </span> {{celeb.fertility}} </p>
        <p> <span class="celeb-prop"> Favorite Book: </span> {{celeb.book}} </p>
        <p> <span class="celeb-prop"> Bio: </span> {{celeb.bio}} </p>
        <p> <span class="celeb-prop"> Ladder Rating: </span> {{celeb.ladder_guess}} </p>
        <div class="image">
            <label>
                <figure> <img v-bind:src="celeb.pic" alt="celeb.name" width="200"></figure>
            </label>
        </div>
        <div class='input-button-container'>
            <button v-on:click="onRemove(celeb)">remove this celeb</button>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    celeb: Object,
    onRemove: Function
  }
};

</script>

<style scoped>
.racist {color: red}
</style>