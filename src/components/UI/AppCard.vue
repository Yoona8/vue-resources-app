<template>
  <div class="card">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'app-card'
}
</script>

<style scoped>
.card {
  padding: 20px 30px;
  border: 1px solid var(--c-neutral);
  border-radius: 10px;
  box-shadow: var(--basic-box-shadow);
}
</style>
