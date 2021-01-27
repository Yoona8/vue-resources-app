<template>
  <article class="resource">
    <h2 class="resource__title">
      <a :href="url">
        {{ name }}
      </a>
    </h2>
    <p class="resource__description">{{ description }}</p>
    <app-button
      type="button"
      @click="onCompleteClick"
    >Complete</app-button>
  </article>
</template>

<script>
import AppButton from '@/components/UI/AppButton';

export default {
  name: 'resource-item',
  components: {AppButton},
  props: {
    id: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    description: String,
    url: String,
    isFinished: Boolean
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

<style scoped>
.resource {
  max-width: 500px;
  margin: 0 auto;
}

.resource__title {
  margin: 0 0 20px;
  font-weight: 600;
  font-size: 24px;
}
</style>
