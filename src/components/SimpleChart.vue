<template>
  <div class="chart-detail">
      <b-card
        class="card-chart"
        header="Chart"
        header-tag="header"
    >

    <div class="card-info">
        <div class="card-title">
            <h2>Daily Block Reward</h2>
        </div>

        <b-card-text class="card-desc">100 blocks per day</b-card-text>

    </div>

    <div class="card-content">
        <apexchart type="bar"
        width="800px" height="400" :options="options" :series="series"></apexchart>
    </div>

    </b-card>

  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
import VueApexCharts from 'vue-apexcharts';

@Component({
  data() {
    return {
      options: {
        chart: {
          id: 'vuechart-example',
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      },
      series: [{
        name: 'series-1',
        data: [30, 40, 45, 50, 49, 60, 70, 91],
      }],
    };
  },
  components: {
    apexchart: VueApexCharts,
  },
})
export default class SimpleChart extends Vue {}
</script>

<style>
.chart-detail {
    display: flex;
}

.card-chart {
    margin: auto;
}

.card-content {
    padding: 0px 10px;
}

.card-info {
    text-align: center;
}

</style>
