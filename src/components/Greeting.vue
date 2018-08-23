<template>
    <div class="hello">
        <img alt="Alchemy logo" src="../../img/alchemy.jpg">
        <h1>{{msg}}</h1>
    </div>
</template>

<script>
export default {
  name: 'Greeting',
  props: {
    msg: String
  }
};
</script>

<style scoped>
.hello {
    background-color: black;
    color: white;
}
</style>
