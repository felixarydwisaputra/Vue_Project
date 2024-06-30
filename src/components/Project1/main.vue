<script setup>
  import {ref} from 'vue'

  const newTask = ref('')
  const tasks = ref([])

  const addTask = () => {
    if (!newTask.value) return
    tasks.value.push(newTask.value)
    newTask.value = ''
  }

  const removeTask = (i) => {
    tasks.value.splice(i, 1)
  }

</script>


<template>
  <div class="container">
    <div class="card">
      <h1>Add New Task</h1>
      <div class="form">
        <input type="text" v-model="newTask" placeholder="Input your next task" @keyup.enter="addTask">
        <button @click="addTask">Add Task</button>
      </div>
      <div v-for="(task, i) in tasks" key="i">
        <div class="tasks">
          <h3>{{task}}</h3>
          <button @click="removeTask(i)">Delete Task</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .container{
    font-family: sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 90dvh;  
    min-width: 100%;
  }

  .card{
    padding: 1rem 3rem;
    padding-bottom: 2rem;
    min-width: 30%;
    box-shadow: 1px 1px 10px #ccc;
    border-radius: 10px;
  }

  .form{
    display: flex;
    justify-content: space-evenly;
    width: 100%;
    margin: 2rem 0rem;
  }

  .form button{
    width: 30%;
    background-color: greenyellow;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 14px;
    box-shadow: 1px 1px 10px #ccc;
    font-weight: bold;
    
  }

  input{
    width: 100%;
    margin-right: 1rem;
    padding: 1rem 1rem;
    border-radius: 5px;
    font-size: 14px;
  }

  .tasks{
    display: flex;
    height: 30px;
    align-items: center;
    background-color: #e9e9e9;
    border-radius: 5px;
    padding: .5rem .5rem;
    justify-content: space-between;
    margin-bottom: 1rem;
  }

  .tasks button{
    background-color: transparent;
    padding: .5rem 1rem;
    border: none;
    border-radius: 5px;
    color: white;
    font-weight: bold;
    background-color: red;
    cursor: pointer;
  }
</style>