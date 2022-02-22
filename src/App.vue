<template>
  <div id="app">
    <h1>로보아르테 과제</h1>
    <div class="Doughnut">
      <doughnut-chart />
    </div>
    <div class="Line">
      <line-chart :width="1200" :height="400" />
    </div>
    <div class="Bar">
      <bar-chart :width="2000" :height="1000" />
    </div>
  </div>
</template>

<script>
import DoughnutChart from "./components/DnChart.vue";
import LineChart from "./components/LineChart.vue";
import BarChart from "./components/BarChart.vue";

export default {
  name: "App",
  components: { DoughnutChart, LineChart, BarChart },
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
.Bar {
  width: 60%;
  margin: auto;
}
</style>
