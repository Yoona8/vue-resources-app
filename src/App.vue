<template>
  <the-header></the-header>
  <resource-list :resources="resources"></resource-list>
  <new-resource
    @resource-added="onResourceAdded"
  ></new-resource>
</template>

<script>
import TheHeader from '@/components/TheHeader';
import ResourceList from '@/components/ResourceList';
import NewResource from '@/components/NewResource';

const generateId = () => {
  return (Date.now() + Math.random()).toString();
};

export default {
  components: {ResourceList, TheHeader, NewResource},
  data() {
    return {
      resources: [{
        id: generateId(),
        name: 'Learn JS',
        url: '',
        description: 'Learn JS with the online textbook.',
        tag: 'javascript',
        isFinished: true
      }, {
        id: generateId(),
        name: 'Learn CSS animations',
        url: '',
        tag: 'css',
        isFinished: false
      }]
    }
  },
  methods: {
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

<style>
:root {
  --c-primary: #DFBAC1;
  --c-primary-dark: #B5A5BF;
  --c-primary-neutral: #D8CCE0;
  --c-neutral: #757DA4;
  --c-black: #13161F;
  --c-black-light: #33394F;
  --basic-transition: 0.2s ease-in-out;
}

body,
html {
  margin: 0;
  padding: 0;
}

body {
  min-width: 375px;
  font-family: 'Work Sans', Arial, sans-serif;
  color: var(--c-black);
}

button,
input {
  font: inherit;
}
</style>
