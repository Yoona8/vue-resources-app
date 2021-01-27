<template>
  <p class="input">
    <slot></slot>
  </p>
</template>

<script>
export default {
  name: 'app-input'
}
</script>

<style>
.input {
  margin: 0;
}

.input input {
  display: block;
}
</style>
