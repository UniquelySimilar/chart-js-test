<template>
  <div class="chart-test">
    <h3>Chart Test</h3>
    <canvas id="chart-canvas" width="400" height="400" ref="chartref"></canvas>
  </div>
</template>

<script>
  import Chart from 'chart.js';
  import { sampleBarConfig } from '@/chart-configurations.js'

  export default {
    data() {
      return {
        chartObj: null,
        sampleBarConfig
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
        this.sampleBarConfig.data.datasets[0].data = this.chartData;
      }
    },
    mounted() {
      this.setChartData();
      this.chartObj = new Chart(this.$refs.chartref, sampleBarConfig);
    },
    // beforeDestroy() {
    //   // This necessary if canvas is reused for a new chart
    //   this.chartObj.destroy();
    // }
  }
</script>