<template>
  <h1>Users</h1>
</template>

<script>
export default {
  methods: {
    async fetchUsers() {
      try {
        let res = await fetch("https://jsonplaceholder.typicode.com/users");
        let data = await res.json();
        console.log("data", data);
      } catch (err) {
        console.log("error", err);
      }
    },
  },
  mounted() {
    this.fetchUsers();
  },
};
</script>

<style></style>
