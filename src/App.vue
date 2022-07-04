<script setup lang="ts">
import BarChart from "./components/BarChart.vue";
import LineChart from "./components/LineChart.vue";

const chartData = {
  labels: ["January", "February", "March"],
  datasets: [{ data: [40, 20, 12], fill: "start", backgroundColor: "#444" }],
};

const options = {
  responsive: true,
  maintainAspectRatio: false,
  scales: {
    yAxes: [
      {
        ticks: { reverse: false, start: 0 },
        min: 0,
        beginAtZero: true,
      },
    ],
    xAxes: [
      {
        ticks: { display: true },
        type: "time",
        time: { parser: "DD/MM/YYYY", unit: "day" },
      },
    ],
  },
  legend: { display: "bottom" },
};
</script>

<template>
  <LineChart :chartData="chartData" :options="options" />
  <BarChart :chartData="chartData" :options="options" />
</template>

<style></style>
