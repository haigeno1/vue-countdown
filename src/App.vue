<template>
  <ProgressBar v-for="(time, i) in [9, 8, 7, 6, 5]" :value="time" :key="i" />
</template>

<script>
import ProgressBar from "./components/ProgressBar.vue";

export default {
  name: "App",
  components: {
    ProgressBar,
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
