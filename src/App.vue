<template>
<div class="container mt-5">
  <h1 class="mb-4">Interactive Dashboard</h1>

  <!-- Cards -->
  <DashboardCards />

  <!-- Filter -->
  <FilterDropdown @update="filterData" />

  <!-- Chart -->
  <LineChart :chart-data="chartData" :chart-labels="chartLabels" />

  <!-- Table -->
  <DataTable :table-data="tableData" />
</div>
</template>

<script>
import DashboardCards from './components/DashboardCards.vue';
import FilterDropdown from './components/FilterDropdown.vue';
import LineChart from './components/LineChart.vue';
import DataTable from './components/DataTable.vue';

export default {
components: { DashboardCards, FilterDropdown, LineChart, DataTable },
data() {
  return {
    chartLabels: ['Jan','Feb','Mar','Apr','May','Jun'],
    chartData: [12,19,14,21,17,25],
    tableData: [
      { month:'Jan', users:20, sales:30, orders:12, revenue:'$1.2K' },
      { month:'Feb', users:25, sales:40, orders:15, revenue:'$1.5K' },
      { month:'Mar', users:22, sales:35, orders:13, revenue:'$1.3K' },
      { month:'Apr', users:28, sales:45, orders:18, revenue:'$1.8K' },
      { month:'May', users:30, sales:50, orders:20, revenue:'$2.0K' },
      { month:'Jun', users:35, sales:55, orders:22, revenue:'$2.2K' }
    ]
  };
},
methods:{
  filterData(option){
    if(option==='Jan-Jun'){
      this.chartLabels=['Jan','Feb','Mar','Apr','May','Jun'];
      this.chartData=[12,19,14,21,17,25];
    } else if(option==='Jul-Dec'){
      this.chartLabels=['Jul','Aug','Sep','Oct','Nov','Dec'];
      this.chartData=[20,18,22,30,25,28];
    } else{
      this.chartLabels=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
      this.chartData=[12,19,14,21,17,25,20,18,22,30,25,28];
    }
  }
}
}
</script>
