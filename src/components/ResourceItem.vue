<template>
  <li>{{ name }}</li>
</template>

<script>
export default {
  name: 'resource-item',
  props: {
    name: {
      type: String,
      required: true,
      validator: (value) => {
        return value.length > 2;
      }
    }
  },
  data() {
    return {
      resourceName: 'Some resource'
    };
  }
}
</script>

<style></style>
