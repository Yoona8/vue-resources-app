<template>
  <ul class="resources">
    <li
        class="resources__item"
        v-for="resource in resources"
        :key="resource.id"
    >
      <resource-item
          :id="resource.id"
          :name="resource.name"
          :url="resource.url"
          :tag="resource.tag"
          :description="resource.description"
          :is-finished="resource.isFinished"
          @complete-clicked="onCompleteClicked"
      ></resource-item>
    </li>
  </ul>
</template>

<script>
import ResourceItem from '@/components/ResourceItem';

export default {
  name: 'resource-list',
  components: {ResourceItem},
  props: ['resources'],
  methods: {
    onCompleteClicked(resourceId) {
      const resource = this.resources.find((item) => item.id === resourceId);

      resource.isFinished = !resource.isFinished;
    }
  }
}
</script>

<style scoped>
.resources {
  max-width: 600px;
  margin: 0 auto 40px;
  padding: 0;
  list-style: none;
}

.resources__item {
  padding: 20px 30px;
  border: 1px solid var(--c-neutral);
  border-radius: 10px;
  box-shadow: var(--basic-box-shadow);
}

.resources__item:not(:last-child) {
  margin-bottom: 20px;
}
</style>
