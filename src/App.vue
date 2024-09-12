<script>
  export default {
    data() {
      return {
        name: 'John Doe',
        status: 'active',
        tasks: ['tast one', 'tasks two', 'tasks three'],
        link: 'https://www.google.com'
      };
    },
    methods: {
      toggleStatus() {
        if (this.status == 'active') {
          this.status = 'pending'
        } else if (this.status == 'pending') {
          this.status = 'inactive'
        } else {
          this.status = 'active'
        }
      }
    }
  }
</script>

<template>
  <h1>{{ name }}</h1>

  <br>

  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <br>

  <h3>Tasks</h3>

  <br>
  <ul>

    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <br>
  <!-- <a v-bind:href="link">Google</a> -->
  <a :href="link">Google</a>

  <br>
  <!-- <button v-on:click="toggleStatus">Change Status</button> -->
  <button @click="toggleStatus">Change Status</button>
</template>