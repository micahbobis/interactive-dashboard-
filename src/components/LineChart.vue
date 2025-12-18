<template>
<div class="p-4 border rounded shadow-sm mb-4" style="height:300px;">
  <canvas ref="chartRef"></canvas>
</div>
</template>

<script>
import { onMounted, ref, watch } from 'vue';
import Chart from 'chart.js/auto';

export default {
props: ['chartData', 'chartLabels'],
setup(props) {
  const chartRef = ref(null);
  let chartInstance = null;

  const renderChart = () => {
    if(chartInstance) chartInstance.destroy();
    chartInstance = new Chart(chartRef.value, {
      type: 'line',
      data: {
        labels: props.chartLabels,
        datasets: [{
          label: 'Sales',
          data: props.chartData,
          borderColor:'#1E3A8A',
          backgroundColor:'rgba(30,58,138,0.2)',
          fill:true,
          tension:0.4,
          pointRadius:5,
          pointHoverRadius:8,
          pointBackgroundColor:'#1E3A8A'
        }]
      },
      options: { responsive:true, maintainAspectRatio:false }
    });
  };

  onMounted(renderChart);
  watch([() => props.chartData, () => props.chartLabels], renderChart);

  return { chartRef };
}
}
</script>
