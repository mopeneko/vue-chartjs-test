<script lang="ts">
import { Component, Vue, Prop, Mixins } from "vue-property-decorator";
import Chart from "chart.js";
import VueChart from "vue-chartjs";
const Bar = VueChart.Bar;
const reactiveProp = VueChart.mixins.reactiveProp;

@Component
export default class ChartBar extends Mixins(Bar, reactiveProp) {
  @Prop({ default: {} }) chartData: Chart.ChartData;
  @Prop({ default: {} }) options: Chart.ChartOptions;

  mounted() {
    this.renderChart(this.chartData, this.options);
  }
}
</script>
