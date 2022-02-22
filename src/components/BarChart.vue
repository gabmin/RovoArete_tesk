<script>
import { HorizontalBar } from "vue-chartjs";
import data from "../assets/data.json";

const maueData = data.map((e) => e.menu_name);
const mauecnt = maueData.reduce((acc, cur) => {
  acc[cur] = (acc[cur] || 0) + 1;
  return acc;
}, {});

export default {
  extends: HorizontalBar,
  data: () => ({
    chartdata: {
      labels: Object.keys(mauecnt).reverse(),
      datasets: [
        {
          backgroundColor: "#198DF0",
          barThickness: 10,
          data: Object.values(mauecnt).reverse(),
        },
      ],
      options: {
        reverse: true,
        legend: {
          display: false,
        },
      },
    },
  }),
  mounted() {
    this.renderChart(this.chartdata, this.options);
  },
};
</script>
