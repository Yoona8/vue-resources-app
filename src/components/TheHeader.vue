<template>
  <header class="header">
    <h1 class="page-title">Library</h1>
  </header>
</template>

<script>
export default {
  name: 'the-header'
}
</script>

<style scoped>
.header {
  margin-bottom: 40px;
  padding: 20px;
  text-align: center;
  color: var(--c-primary-neutral);
  background-color: var(--c-black-light);
}

.page-title {
  margin: 0;
  font-weight: 600;
  font-size: 40px;
}
</style>
