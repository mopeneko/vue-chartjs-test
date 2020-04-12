<template>
  <div id="app">
    <div class="chart-container">
      <ChartBar :chartData="chartData" :options="chartOption" :styles="chartStyles" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import { ChartData, ChartOptions } from "chart.js";
import ChartBar from "./components/ChartBar.vue";

@Component({ components: { ChartBar } })
export default class App extends Vue {
  private chartData: ChartData = {
    labels: ["A", "B", "C", "D", "E"],
    datasets: [
      {
        label: "Data One",
        data: [1, 5, 3, 4, 3]
      }
    ]
  };

  private chartOption: ChartOptions = {
    maintainAspectRatio: false
  };

  private chartStyles = {
    height: "100%",
    width: "100%"
  };
}
</script>

<style>
.chart-container {
  position: relative;
  height: 40vh;
  width: 80vw;
  margin: 0 auto;
}
</style>
