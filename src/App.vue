<template>
  
  <div id="app">
    <Greeting msg="Welcome to Alchemy Code Lab!"/>
    <ClassList v-bind:persons="persons" v-bind:onRemove="handleRemove"/>
    <AddPerson v-bind:onAdd="handleAdd"/>
  </div>
</template>

<script>
import Greeting from './components/Greeting.vue';
import persons from './persons';
import ClassList from './components/ClassList.vue';
import AddPerson from './components/AddPerson';

export default {
  name: 'app',
  data() {
    return { persons };
  },
  components: {
    AddPerson,
    Greeting,
    ClassList
  },
  methods: {
    handleAdd(person) {
      this.persons.push(person);
    },
    handleRemove(person) {
      const index = this.persons.indexOf(person);
      if(index !== -1) {
        this.persons.splice(index, 1);
      }
    }
  }
};

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
 }




</style>
