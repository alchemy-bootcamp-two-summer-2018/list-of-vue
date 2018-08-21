<template>
  <li>
    {{cocktail.name}}
      
      

  </li>
</template>

<script>
export default {
  name: 'Cocktail',
  props: {
      cocktail: Object,
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>