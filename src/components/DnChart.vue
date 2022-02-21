<script>
import { Doughnut } from "vue-chartjs";
import data from "../assets/data.json";

const id01 = data.filter((info) => {
  return info.user_id === "00001";
});
const id03 = data.filter((info) => {
  return info.user_id === "00003";
});
const id04 = data.filter((info) => {
  return info.user_id === "00004";
});
const id05 = data.filter((info) => {
  return info.user_id === "00005";
});
const id06 = data.filter((info) => {
  return info.user_id === "00006";
});

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
          data: [
            id01.length,
            id03.length,
            id04.length,
            id05.length,
            id06.length,
          ],
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
