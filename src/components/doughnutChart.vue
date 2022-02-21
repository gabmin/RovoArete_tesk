<template>
  <div id="doughnut-chart">
    <div class="box">
      <div class="title">과일 선호도 조사</div>
      <div class="chart">
        <doughnut-chart
          ref="fruitChart"
          :chartData="chart.data"
          :options="chart.options"
          id="chart"
        ></doughnut-chart>
      </div>
    </div>
  </div>
</template>

<script>
import DoughnutChart from "./doughnutChart.js";

export default {
  name: "doughnut-chart",
  type: "doughnut",
  components: { DoughnutChart },
  data() {
    return {
      chart: {
        data: {
          labels: ["1호점", "3호점", "4호점", "5호점", "6호점"],
          datasets: [
            {
              backgroundColor: [
                "#91CB74",
                "#74BFDD",
                "#EE6668",
                "#FAC859",
                "#5D7AD8",
              ],
              data: [1, 4, 2, 3, 5],
            },
          ],
        },
        options: {
          plugins: {
            legend: {
              display: true,
              position: top,
              labels: {
                pointStyle: "rectangle",
                font: {
                  size: 14,
                },
              },
              align: "center",
            },
          },
        },
      },
    };
  },
};
</script>
