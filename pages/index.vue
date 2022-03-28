<template>
  <main>
    <h1>Todo App</h1>
    <p>Create a list of tasks</p>

    <div class="create-new">
      <input 
      type="text" 
      v-model="newTask" 
      placeholder="Add a new task" 
      @keypress.enter="addTask" />
      <button @click="addTask">Add</button>
    </div>

    <div class="tasks">

    </div>


  </main>
</template>

<script>
export default {
  data(){
    return {
      newTask: ''
    }
  },
  methods: {
    addTask () {
      if (this.newTask){
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask = '';
      }
    }
  }
}
</script>
