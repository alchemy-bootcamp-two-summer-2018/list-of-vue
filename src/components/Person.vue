<template>
    <div class="container">
        <div v-if="person.position === 'Instructor'" class="element">
            <img alt="teacher" src="../../img/teacher.jpg">
            <h4 >{{ person.name }} is an {{ person.position }} who is from {{ person.from}}</h4>
        </div>
        <div v-else-if="person.position === 'TA'" class="element">
            <img alt="assistant" src="../../img/assistant.png">
          <h4>{{ person.name }} is a {{ person.position }} who is from {{ person.from }}</h4>  
        </div>
        <div v-else class="element">
            <img alt="teacher" src="../../img/student.jpg">
            <h4>{{ person.name }} is a {{ person.position }} who is from {{ person.from }}</h4>
        </div>           
        <button v-on:click="onRemove(person)" id="dropped-out">Dropped Out</button>          
    </div>
  
</template>

<script>



export default {
  props: {
    person: Object,
    onRemove: Function
  }
};

</script>

<style scoped>
    img {
        height: 75px;
        margin-right: 50px;
    }
</style>
