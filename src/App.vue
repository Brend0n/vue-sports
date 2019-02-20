<template>
  <div id="app">
    <teampage></teampage>
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import teampage from "./pages/Teams.vue";

export default {
  name: "app",
  components: {
    // HelloWorld,
    teampage
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
