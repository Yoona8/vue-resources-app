<template>
  <a class="link" :href="url">
    <slot></slot>
  </a>
</template>

<script>
export default {
  name: 'app-link',
  props: ['url']
}
</script>

<style scoped>
.link {
  text-decoration: none;
  color: inherit;
}

.link:hover {
  text-decoration: underline;
}
</style>
