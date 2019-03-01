<template>
  <div class="container">
    <div class="win"></div>
    <div class="draw"></div>
    <div class="lost"></div>
  </div>
</template>

<script>
export default {
  name: "BarChart",
  props: {
    win: {
      type: Number
    },
    draw: {
      type: Number
    },
    lost: {
      type: Number
    }
  },

  computed: {}
};
</script>

<style scoped>
.container {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 10px;
}
.win {
  background-color: green;
}
</style>
