<template>
  <PolarAreaChart :chartData="polarAreaData" />
</template>
  
<script lang="ts">
import { defineComponent } from 'vue';
import { PolarAreaChart } from 'vue-chart-3';
import { Chart, registerables } from "chart.js";

Chart.register(...registerables);

export default defineComponent({
  name: 'Home',
  components: { PolarAreaChart },
  setup() {
    const polarAreaData = {
      labels: ['Paris', 'Nîmes', 'Toulon', 'Perpignan', 'Autre'],
      datasets: [
        {
          data: [30, 40, 60, 70, 5],
          backgroundColor: ['#77CEFF', '#0079AF', '#123E6B', '#97B0C4', '#A5C8ED'],
        },
      ],
    };

    return { polarAreaData };
  },
});
</script>
