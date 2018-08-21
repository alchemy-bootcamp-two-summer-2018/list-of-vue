<template>

  <section class="flex-container">

    <AddCat v-bind:onAdd="handleAdd"/>
    <CatList v-bind:cats="cats" v-bind:onRemove="handleRemove"/>
    
  </section>
  
</template>

<script>
import CatList from './components/CatList.vue';
import AddCat from './components/AddCat.vue';
import cats from './cats.js';


export default {
  name: 'app',
  data() {
    return { cats };
  },
  components: {
    AddCat,
    CatList
  },

  methods: {
    handleAdd(cat){
      this.cats.push(cat);
    },
    handleRemove(cat){
      const index = this.cats.indexOf(cat);
      if(index !== -1) {
        this.cats.splice(index, 1);
      }
    }
  
  }

};
</script>


<style scoped>

.flex-container {
  display:flex;
}

</style>
