<template>
  <div id="app">
    <h1>로보아르테 과제</h1>
    <div class="chart">
      <div v-for="sort in chart" :key="sort">
        <button @click="state = sort">{{ sort }}</button>
      </div>
    </div>
    <div class="Doughnut" v-if="state === `doughnut`">
      <h3>각 매장 별 주문 건수</h3>
      <doughnut-chart />
    </div>
    <div class="Line" v-if="state === `line`">
      <h3>요일 별 주문 건수</h3>
      <line-chart :width="1200" :height="400" />
    </div>
    <div class="Bar" v-if="state === `bar`">
      <h3>메뉴 별 주문 건수</h3>
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
    return {
      chart: ["doughnut", "line", "bar"],
      state: "doughnut",
    };
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
.chart {
  width: 60%;
  height: 40px;
  background-color: darkslateblue;
  border-radius: 3px;
  display: flex;
  justify-content: space-around;
  margin: 30px auto;
}
.chart button {
  width: 100px;
  color: white;
  border: none;
  background-color: transparent;
  font-size: 20px;
  padding: 8px;
  cursor: pointer;
  font-weight: bold;
}
button:hover {
  color: orange;
}
.Doughnut {
  width: 600px;
  margin: auto;
}
h3 {
  width: 220px;
  display: inline-block;
  background-color: orange;
  border-radius: 20px;
}
</style>
