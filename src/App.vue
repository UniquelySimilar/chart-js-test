<template>
  <div id="app">
    <chart-test v-if="dataReady" :chartData="pieChartData" />
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
        dataReady: true
      }
    },
    methods: {
      getData() {
        this.dataReady = true;
      }
    },
    // mounted() {
    //   // Simulate API call
    //   setTimeout(this.getData(), 2000);
    // }
  }
</script>

<style>

</style>