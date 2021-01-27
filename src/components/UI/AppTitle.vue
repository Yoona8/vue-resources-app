<template>
  <h2 class="title">
    <slot></slot>
  </h2>
</template>

<script>
export default {
name: 'app-title'
}
</script>

<style scoped>
.title {
  margin: 0 0 20px;
  font-weight: 600;
  font-size: 24px;
}
</style>
