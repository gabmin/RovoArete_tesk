<script>
import { Doughnut } from "vue-chartjs";

export default {
  extends: Doughnut,
  data: () => ({
    chartdata: {
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
      options: {},
    },
  }),
  mounted() {
    this.renderChart(this.chartdata, this.options);
  },
};
</script>
