<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'app-button'
}
</script>

<style scoped>
.button {
  display: inline-block;
  margin: 0;
  padding: 10px 20px;
  font-size: 16px;
  text-align: center;
  color: var(--c-primary-neutral);
  background-color: var(--c-black-light);
  border: 2px solid var(--c-black-light);
  border-radius: 20px;
  transition: var(--basic-transition);
}

.button:not(:disabled) {
  cursor: pointer;
}

.button:not(:disabled):hover {
  color: var(--c-black-light);
  background-color: var(--c-primary-neutral);
}

.button:disabled {
  background-color: var(--c-neutral);
  border-color: var(--c-neutral);
}
</style>
