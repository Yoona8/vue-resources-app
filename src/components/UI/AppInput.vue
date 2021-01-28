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
  margin: 0 0 20px;
}

.input input,
.input textarea,
.input select {
  display: block;
  width: 100%;
  min-height: 46px;
  box-sizing: border-box;
  margin: 0;
  padding: 10px 15px;
  font-size: 18px;
  line-height: 24px;
  border: 1px solid var(--c-neutral);
  border-radius: 4px;
  transition: var(--basic-transition);
}

.input input:focus,
.input textarea:focus,
.input select:focus {
  border-color: var(--c-primary);
  background-color: var(--c-primary-opaque);
  outline: none;
}

.input input:hover,
.input textarea:hover,
.input select:hover {
  border-color: var(--c-primary);
}

.input textarea {
  resize: none;
}

.input label {
  display: block;
  margin-bottom: 2px;
}
</style>
