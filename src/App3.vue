<script setup>
import { ref, onMounted } from 'vue';

    const name = ref('John Doe');
    const status = ref('active');
    const tasks = ref(['task1', 'task2', 'task3']);
    const newTask = ref('');
    // const link = 'https://google.com';

    const toggleStatus = () => {
      status.value === 'active' ? status.value = 'pending' : status.value = 'active';
    };
    const addTask = () => {
      if (newTask.value.trim !== '') {
      tasks.value.push(newTask.value);
      newTask.value = '';
      }
    };
    const deleteTask = (index) => {
      tasks.value.splice(index, 1);
    };  

    // return { name, status, tasks, toggleStatus };
  
    onMounted(async () => {
      try {
        const res = await fetch('https://jsonplaceholder.typicode.com/todos');
        const data = await res.json();
        tasks.value = data.map((task) => task.title);
        console.log(data);
      } catch (error) {
        console.log('error fetching tasksss'); 
      }
    });


</script>

<template>
    <h1>{{name}}</h1>
    <p v-if="status === 'active'">user is activeee</p>
    <p v-else-if="status === 'pending'">user is pending</p>
    <p v-else>user is not active</p>

    <form @submit.prevent="addTask">
      <label for="task">Add Task</label>
      <input type="text" id="task" name="newTask" v-model="newTask" />
      <button type="submit">Submitttt</button>
    </form>
    
    <h3>Tasks</h3>
    <ul>
      <li v-for="(task, index) in tasks" :key="task">
        <span>{{task}}</span> 
        <button @click="deleteTask(index)">xxxx</button>
      </li>
    </ul>
    <!-- <a v-bind:href="link">click for Googleeee</a>
    <a href="link">click for Googleexx</a> -->
    <br />
    <!-- <button v-on:click="toggleStatus">Change statusss</button> -->
    <button @click="toggleStatus">Change statusssxx</button>
</template>

<style scoped>
h1 {
  color: red;
}

</style>
