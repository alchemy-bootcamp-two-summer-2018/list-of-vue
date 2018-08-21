<template>

  <li class ="cat-profile">
    <img :src=cat.img >
    <h3> {{cat.name}} </h3>
    <p v-if="cat.age > 10 ">
        performing on May 12th
      <p v-else> performing on May 13th</p>
    <p> <button v-on:click="onRemove(cat)"> X Remove Your Cat </button> </p>
  </li>

</template>

<script>
export default {
  props: {
    cat: Object,
    onRemove: Function
  } 
};

</script>


<style scoped>

.cat-profile { 
  width: 250px;
  background-color: white;
  padding: 20px;
  border: solid 1px #7669e752;
  margin-right:20px;
  margin-top: 20px;
  
  
}

button {
  color: #e769bf;
  background: none;
  border: none;
  border-bottom: solid 2px #27b0e4;
  padding: 0;
  padding-bottom: 5px;
  font-size: 13px;
}



</style>
