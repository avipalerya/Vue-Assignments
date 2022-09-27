<template>
  <valid-gym />
  <!-- <gym-form /> -->
  <!-- <fetch-data /> -->
</template>

<script>
import ValidGym from "./components/Valid-Gym.vue";
// import FetchData from "./components/FetchData.vue";
// import GymForm from "./components/GymForm.vue";

export default {
  name: "App",
  components: {
    ValidGym,
    // FetchData,
    // GymForm,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
