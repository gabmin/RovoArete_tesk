<script>
import { Doughnut } from "vue-chartjs";
import data from "../assets/data.json";

// 매장별 주문 건수 데이터 분류
const filterId = (userId) => {
  const filterCnt = data.filter((info) => {
    return info.user_id === userId;
  }).length;
  return filterCnt;
};

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
            filterId("00001"),
            filterId("00003"),
            filterId("00004"),
            filterId("00005"),
            filterId("00006"),
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
