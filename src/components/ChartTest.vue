<template>
  <div class="chart-test">
    <h3>Chart Test</h3>
    <canvas id="chart-canvas" width="500" height="500" ref="chartref"></canvas>
  </div>
</template>

<script>
  import Chart from 'chart.js';
  import { sampleLineConfig } from '@/chart-configurations.js'

  export default {
    data() {
      return {
        chartObj: null,
        chartConfig: sampleLineConfig
      }
    },
    props: {
      chartData: {
        type: Array,
        required: true
      }
    },
    methods: {
      setChartData() {
        this.chartConfig.data.datasets[0].data = this.chartData;
      }
    },
    mounted() {
      this.setChartData();
      this.chartObj = new Chart(this.$refs.chartref, this.chartConfig);
    },
    // beforeDestroy() {
    //   // This necessary if canvas is reused for a new chart
    //   this.chartObj.destroy();
    // }
  }
</script>