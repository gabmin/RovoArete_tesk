<script>
import { Line } from "vue-chartjs";
import data from "../assets/data.json";

const fitherFn = (id, week) => {
  const filtered = data.filter((info) => {
    return info.user_id === id && info.week === week;
  });
  return filtered.length;
};

export default {
  extends: Line,
  data: () => ({
    chartdata: {
      labels: ["Mon", "Tue", "Wen", "Thu", "Fri", "Sat", "Sun"],
      datasets: [
        {
          label: "1호점",
          borderColor: "#91CB74",
          pointBackgroundColor: "#91CB74",
          lineTension: 0.1,
          borderWidth: 2,
          fill: false,
          data: [
            { x: "Mon", y: fitherFn("00001", "월요일") },
            { x: "Tue", y: fitherFn("00001", "화요일") },
            { x: "Wen", y: fitherFn("00001", "수요일") },
            { x: "Thu", y: fitherFn("00001", "목요일") },
            { x: "Fri", y: fitherFn("00001", "금요일") },
            { x: "Sat", y: fitherFn("00001", "토요일") },
            { x: "Sun", y: fitherFn("00001", "일요일") },
          ],
        },
        {
          label: "3호점",
          borderColor: "#74BFDD",
          pointBackgroundColor: "#74BFDD",
          lineTension: 0.1,
          borderWidth: 2,
          fill: false,
          data: [
            { x: "Mon", y: fitherFn("00003", "월요일") },
            { x: "Tue", y: fitherFn("00003", "화요일") },
            { x: "Wen", y: fitherFn("00003", "수요일") },
            { x: "Thu", y: fitherFn("00003", "목요일") },
            { x: "Fri", y: fitherFn("00003", "금요일") },
            { x: "Sat", y: fitherFn("00003", "토요일") },
            { x: "Sun", y: fitherFn("00003", "일요일") },
          ],
        },
        {
          label: "4호점",
          borderColor: "#EE6668",
          pointBackgroundColor: "#EE6668",
          lineTension: 0.1,
          borderWidth: 2,
          fill: false,
          data: [
            { x: "Mon", y: fitherFn("00004", "월요일") },
            { x: "Tue", y: fitherFn("00004", "화요일") },
            { x: "Wen", y: fitherFn("00004", "수요일") },
            { x: "Thu", y: fitherFn("00004", "목요일") },
            { x: "Fri", y: fitherFn("00004", "금요일") },
            { x: "Sat", y: fitherFn("00004", "토요일") },
            { x: "Sun", y: fitherFn("00004", "일요일") },
          ],
        },
        {
          label: "5호점",
          borderColor: "#FAC859",
          pointBackgroundColor: "#FAC859",
          lineTension: 0.1,
          borderWidth: 2,
          fill: false,
          data: [
            { x: "Mon", y: fitherFn("00005", "월요일") },
            { x: "Tue", y: fitherFn("00005", "화요일") },
            { x: "Wen", y: fitherFn("00005", "수요일") },
            { x: "Thu", y: fitherFn("00005", "목요일") },
            { x: "Fri", y: fitherFn("00005", "금요일") },
            { x: "Sat", y: fitherFn("00005", "토요일") },
            { x: "Sun", y: fitherFn("00005", "일요일") },
          ],
        },
        {
          label: "6호점",
          borderColor: "#74BFDD",
          pointBackgroundColor: "#74BFDD",
          lineTension: 0.1,
          borderWidth: 2,
          fill: false,
          data: [
            { x: "Mon", y: fitherFn("00006", "월요일") },
            { x: "Tue", y: fitherFn("00006", "화요일") },
            { x: "Wen", y: fitherFn("00006", "수요일") },
            { x: "Thu", y: fitherFn("00006", "목요일") },
            { x: "Fri", y: fitherFn("00006", "금요일") },
            { x: "Sat", y: fitherFn("00006", "토요일") },
            { x: "Sun", y: fitherFn("00006", "일요일") },
          ],
        },
      ],
    },
    options: {
      responsive: false,
      legend: {
        display: true,
        position: "right",
        labels: {
          boxWidth: 10,
          fontSize: 17,
          padding: 10,
          usePointStyle: true,
          pointStyle: "circle",
        },
      },
      scales: {
        yAxes: [
          {
            ticks: {
              beginAtZero: true,
              stepSize: 20,
              max: 120,
              min: 0,
              padding: 10,
            },
          },
        ],
      },
    },
  }),
  mounted() {
    this.renderChart(this.chartdata, this.options);
  },
};
</script>
