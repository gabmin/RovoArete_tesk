<script>
import { HorizontalBar } from "vue-chartjs";
import data from "../assets/data.json";

// 메뉴 종류 데이터
const maueData = data.map((e) => e.menu_name);
// 메뉴당 개수
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
          label: "최근 1000개의 주문 중 메뉴별 조리 수량",
          backgroundColor: "#198DF0",
          barThickness: 10,
          data: Object.values(mauecnt).reverse(),
        },
      ],
      options: {
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
