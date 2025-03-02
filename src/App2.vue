<script>

export default {
  data() {
    return {
      name: 'Johnnn Doeee',
      status: 'actdddive',
      tasks: [ 'Task One', 'Task Two', 'Task Three'],
      link: 'https://www.google.com'
     }
  },
  methods: {
    toggleStatus() {
      this.status = this.status === 'active' ? 'pending' : 'active';
    }
  }
}
</script>

<template>
    <h1>{{name}}</h1>
    <p v-if="status === 'active'">user is activeee</p>
    <p v-else-if="status === 'pending'">user is pending</p>
    <p v-else>user is not active</p>
    <h3>Tasks</h3>
    <ul>
      <li v-for="task in tasks" :key="task">{{task}} </li>
    </ul>
    <!-- <a v-bind:href="link">click for Googleeee</a> -->
    <a href="link">click for Googleexx</a>
    <br />
    <!-- <button v-on:click="toggleStatus">Change statusss</button> -->
    <button @click="toggleStatus">Change statusssxx</button>
</template>

<style scoped>
h1 {
  color: red;
}

</style>
