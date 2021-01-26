<template>
  {{ title }}
  <ul>
    <resource-item
      v-for="resource in resources"
      :key="resource.id"
      :name="resource.name"
    ></resource-item>
  </ul>
</template>

<script>
import ResourceItem from '@/components/ResourceItem';
export default {
  components: {ResourceItem},
  data() {
    return {
      title: 'Hello!',
      resources: [{
        id: Date.now() + Math.random(),
        name: 'Learn JS',
        url: '',
        tag: 'javascript',
        isFinished: true
      }, {
        id: Date.now() + Math.random(),
        name: 'Learn CSS animations',
        url: '',
        tag: 'css',
        isFinished: false
      }]
    };
  }
};
</script>

<style></style>
