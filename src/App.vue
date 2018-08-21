<template>
  <div class="grid">
    <MyHeader />
    <AddCeleb v-bind:onAdd="handleAdd"/>
    <CelebList v-bind:celebs="celebs" v-bind:onRemove="handleRemove"/>
    <MyFooter />
  </div>
</template>

<script>
import CelebList from './components/CelebList.vue';
import AddCeleb from './components/AddCeleb.vue';
import MyHeader from './components/MyHeader.vue';
import MyFooter from './components/MyFooter.vue';
import celebs from './celebs';
export default {
  name: 'app',
  data() {
    return { celebs };
  },
  components: {
    MyHeader,
    AddCeleb,
    CelebList,
    MyFooter
  },
  methods: {
    handleAdd(celeb) {
      this.celebs.push(celeb);
    },
    handleRemove(celeb) {
      const index = this.celebs.indexOf(celeb);
      if(index !== -1) {
        this.pirates.splice(index, 1);
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