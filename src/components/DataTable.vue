<template>
<div class="table-responsive mb-4 shadow-sm rounded" style="overflow-x:auto;">
  <table class="table align-middle mb-0 table-hover">
    <thead class="table-dark text-center" style="background-color:#1E3A8A; color:#fff;">
      <tr>
        <th><i class="fas fa-calendar-alt d-block mb-1"></i>Month</th>
        <th><i class="fas fa-users d-block mb-1"></i>Users</th>
        <th><i class="fas fa-chart-line d-block mb-1"></i>Sales</th>
        <th><i class="fas fa-box d-block mb-1"></i>Orders</th>
        <th><i class="fas fa-dollar-sign d-block mb-1"></i>Revenue</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="row in tableData" :key="row.month" class="align-middle">
        <td class="text-center">{{ row.month }}</td>
        <td class="text-center">{{ row.users }}</td>
        <td class="text-center">{{ row.sales }}</td>
        <td class="text-center">{{ row.orders }}</td>
        <td class="text-center">{{ row.revenue }}</td>
      </tr>
    </tbody>
  </table>
</div>
</template>

<script>
export default {
props: ['tableData']
}
</script>

<style scoped>
.table-hover tbody tr {
transition: transform 0.2s ease, background-color 0.2s ease;
}
.table-hover tbody tr:hover {
transform: translateX(5px);
background-color: rgba(30,58,138,0.1);
}
.table th, .table td {
vertical-align: middle;
}
</style>
