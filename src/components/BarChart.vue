
<script>
import { Bar } from "vue-chartjs";

export default {
  extends: Bar,
  data: () => ({
    chartdata: {
      labels: ["January", "February", "March", "April"],
      datasets: [
        {
          label: "Unique Clicks",
          backgroundColor: "#002a61",
          data: [10, 20, 80, 106],
        },
        {
          label: "Non-unique Clicks",
          backgroundColor: "#9bc225",
          data: [2, 5, 24, 35],
        },

        {
          label: "Bot Clicks",
          backgroundColor: "#def1d5",
          data: [1, 7, 12, 22],
        },
      ],
    },
    options: {
      tooltips: {
        displayColors: true,
        callbacks: {
          mode: "x",
        },
      },
      scales: {
        xAxes: [
          {
            stacked: true,
            gridLines: {
              display: false,
            },
          },
        ],
        yAxes: [
          {
            stacked: true,
            ticks: {
              beginAtZero: true,
            },
            type: "linear",
          },
        ],
      },
      responsive: true,
      maintainAspectRatio: false,
      legend: { position: "top" },
    },
  }),

  mounted() {
    this.renderChart(this.chartdata, this.options);
  },
};
</script>