<template>
  <div id="app">
    <chart-test v-if="dataReady" :chartData="lineChartData" />
  </div>
</template>

<script>
  import ChartTest from '@/components/ChartTest'

  export default {
    name: 'App',
    components: {
      ChartTest
    },
    data() {
      return {
        barChartData: [12, 19, 3, 5, 2, 3],
        pieChartData: [10, 20, 30],
        lineChartData: [65, 59, 80, 81, 56, 55, 40],
        dataReady: false
      }
    },
    methods: {
      getData() {
        this.dataReady = true;
      }
    },
    mounted() {
      // Simulate API call
      setTimeout(this.getData(), 1000);
    }
  }
</script>

<style>

</style>