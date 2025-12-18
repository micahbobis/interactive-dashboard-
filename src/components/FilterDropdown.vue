<template>
<div class="mb-4 d-flex justify-content-end">
  <select class="form-select w-auto" @change="$emit('update', $event.target.value)">
    <option>Jan-Jun</option>
    <option>Jul-Dec</option>
    <option>All Year</option>
  </select>
</div>
</template>

<script>
export default {};
</script>
