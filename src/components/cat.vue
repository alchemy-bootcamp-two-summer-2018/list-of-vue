<template>

  <li class="cat-profile">
    <img class="cat-img" :src=cat.img >
    <h3>{{cat.name}} </h3>
    <p><strong>Breed: </strong>{{cat.breed}}</p>
     <p><strong>Hobby: </strong>{{cat.hobby}}</p>
    <p v-if="cat.age > 10 ">
        <strong>Performing on: </strong> May 12th
      <p v-else><strong>Performing on: </strong> May 13th</p>
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
  width: 240px;
  background-color: white;
  padding: 20px;
  border: solid 15px #7669e752;
  margin-right:15px;
  margin-top: 15px;
}

.cat-img {
    border-radius: 100px;
    width: 170px;
}

button {
  color: #e769bf;
  background: none;
  border: none;
  padding: 0;
  margin:0;
  font-size: 13px;
}


</style>
