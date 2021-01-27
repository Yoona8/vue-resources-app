<template>
  <article class="resource">
    <app-title>
      <app-link :url="url">
        {{ name }}
      </app-link>
    </app-title>
    <p class="resource__description">{{ description }}</p>
    <app-button
      type="button"
      @click="onCompleteClick"
    >Complete</app-button>
  </article>
</template>

<script>
import AppButton from '@/components/UI/AppButton';
import AppLink from '@/components/UI/AppLink';
import AppTitle from '@/components/UI/AppTitle';

export default {
  name: 'resource-item',
  components: {AppTitle, AppButton, AppLink},
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
</style>
