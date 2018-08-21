<template>
  <div id="app">
    <img class="header" alt="Dog and Cat Header" src="http://static.tumblr.com/fff16121e816f74cffc899fb0322f811/vv6nlcz/ehAn0rhaz/tumblr_static_animal_header.jpg">
    <CuteAnimalForm v-bind:onAdd="handleAdd" v-bind:cuteAnimals="cuteAnimals"/>
    <CuteAnimalList v-bind:cuteAnimals="cuteAnimals" v-bind:onRemove="handleRemove"/>
  </div>
</template>

<script>
import CuteAnimalForm from './components/CuteAnimalForm.vue';
import cuteAnimals from './cute-animals.js';
import CuteAnimalList from './components/CuteAnimalList.vue';

export default {
  name: 'app',
  data() {
    return { cuteAnimals };
  },
  components: {
    CuteAnimalForm,
    CuteAnimalList
  },
  methods: {
    handleAdd(cuteAnimal) {
      this.cuteAnimals.push(cuteAnimal);
    },
    handleRemove(cuteAnimal) {
      const index = this.cuteAnimals.indexOf(cuteAnimal);
      if(index !== -1) {
        this.cuteAnimals.splice(index, 1);
      }
    }
  }
};
</script>


