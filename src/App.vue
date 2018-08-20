<template>
  <section>
    <img alt="Vue logo" src="./assets/logo.png">
    <p>some random content</p>
    <AddCeleb v-bind:onAdd="handleAdd"/>
    <CelebList v-bind:celebs="celebs" v-bind:onRemove="handleRemove"/>
  </section>
</template>

<script>
import CelebList from './components/CelebList.vue';
import AddCeleb from './components/AddCeleb.vue';
import celebs from './celebs';
export default {
  name: 'app',
  data() {
    return { celebs };
  },
  components: {
    AddCeleb,
    CelebList
  },
  methods: {
    handleAdd(celeb) {
      this.celebs.push(celeb);
    },
    handleRemove(celeb) {
      const index = this.celebs.indexOf(celeb);
      if(index !== -1) {
        this.celebs.splice(index, 1);
      }
    }
  }
};
</script>

<style scoped>
section {
  margin-top: 60px;
}
p {
  color: steelblue;
}
</style>