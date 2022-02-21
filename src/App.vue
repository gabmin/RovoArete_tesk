<template>
  <div id="app">
    <h1>로보아르테 과제</h1>
    <div class="Doughnut">
      <doughnut-chart />
    </div>
  </div>
</template>

<script>
import DoughnutChart from "./components/DnChart.vue";

export default {
  name: "App",
  components: { DoughnutChart },
  data() {
    return {};
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

.Doughnut {
  width: 800px;
  margin: auto;
}
</style>
