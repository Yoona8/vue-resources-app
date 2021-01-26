<template>
  <h1>Library</h1>
  <ul>
    <li
      v-for="resource in resources"
      :key="resource.id"
    >
      <resource-item
        :id="resource.id"
        :name="resource.name"
        @complete-clicked="onCompleteClicked"
      ></resource-item>
    </li>
  </ul>
  <new-resource
    @resource-added="onResourceAdded"
  ></new-resource>
</template>

<script>
import ResourceItem from '@/components/ResourceItem';
import NewResource from '@/components/NewResource';

const generateId = () => {
  return (Date.now() + Math.random()).toString();
};

export default {
  components: {NewResource, ResourceItem},
  data() {
    return {
      title: 'Hello!',
      resources: [{
        id: generateId(),
        name: 'Learn JS',
        url: '',
        tag: 'javascript',
        isFinished: true
      }, {
        id: generateId(),
        name: 'Learn CSS animations',
        url: '',
        tag: 'css',
        isFinished: false
      }]
    };
  },
  methods: {
    onCompleteClicked(resourceId) {
      const resource = this.resources.find((item) => item.id === resourceId);

      resource.isFinished = !resource.isFinished;
    },
    onResourceAdded(resourceName) {
      const resource = {
        id: generateId(),
        name: resourceName,
        url: '',
        tag: '',
        isFinished: false
      };

      this.resources.push(resource);
    }
  }
};
</script>

<style></style>
