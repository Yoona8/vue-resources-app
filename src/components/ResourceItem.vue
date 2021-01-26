<template>
  <article>
    <h2>{{ name }}</h2>
    <button
      type="button"
      @click="onCompleteClick"
    >Complete</button>
  </article>
</template>

<script>
export default {
  name: 'resource-item',
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true,
      validator: (value) => {
        return value.length > 2;
      }
    }
  },
  emits: ['complete-clicked'],
  data() {
    return {
      resourceName: 'Some resource'
    };
  },
  methods: {
    onCompleteClick() {
      this.$emit('complete-clicked', this.id);
    }
  }
}
</script>

<style></style>
