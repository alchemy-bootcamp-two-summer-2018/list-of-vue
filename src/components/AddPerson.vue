<template>
    <form v-on:submit.prevent="handleSubmit">
        <br>
        <div class="container">
            <h5>
                <label >    
                    Name: <input v-model="name" placeholder="Compadre's Name">  
                </label> 
            </h5>
            <h5>
                <label>
                    Position: 
                    <select v-model="position">
                        <option value="Instructor">Instructor</option>
                        <option value="TA">TA</option>
                        <option value="Student">Student</option>
                    </select>
                </label>
            </h5>
            <h5>
                <label>
                    From: <input v-model="from" placeholder="Compadre's From">
                </label>
            </h5>
            <button id="add-compadre">Add Compadre</button>
        </div>
    </form>
</template>
<script>
export default {
  props: {
    onAdd: Function 
  },
  data() {
    return {
      name: '',
      position: '',
      from: ''
    };
  },
  methods: {
    handleSubmit() {
      const newPerson = {
        name: this.name,
        position: this.position,
        from: this.from
      };
      this.onAdd(newPerson);
      this.name = '';
      this.position = '';
      this.from = '';
    }
  }
};
</script>

<style scoped>
    input {
        width: 75%;
    }

    select {
        width: 50%;
    }
    .container {
        background-color: white;
    }
    form {
        background-color: white;
    }
</style>
