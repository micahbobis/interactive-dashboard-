<template>
<div class="row g-3 mb-4">
  <div class="col-6 col-md-3" v-for="card in cards" :key="card.title">
    <div class="card text-center h-100">
      <div class="card-body d-flex flex-column justify-content-center align-items-center">
        <i :class="card.icon" class="fa-2x mb-2"></i>
        <h6>{{ card.title }}</h6>
        <p>{{ card.value }}</p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
data() {
  return {
    cards: [
      { title: 'Users', value: 150, icon: 'fas fa-users' },
      { title: 'Sales', value: 320, icon: 'fas fa-chart-line' },
      { title: 'Orders', value: 85, icon: 'fas fa-box' },
      { title: 'Revenue', value: '$12.4K', icon: 'fas fa-dollar-sign' }
    ]
  };
}
}
</script>
