<template>
  <the-header></the-header>
  <tabs-navigation @tab-clicked="onTabClicked"></tabs-navigation>
  <main class="main">
    <keep-alive>
      <component :is="activeComponent"></component>
    </keep-alive>
  </main>
</template>

<script>
import TheHeader from '@/components/TheHeader';
import ResourceList from '@/components/ResourceList';
import NewResource from '@/components/NewResource';
import TabsNavigation from '@/components/TabsNavigation';

const generateId = () => {
  return (Date.now() + Math.random()).toString();
};

export default {
  components: {TabsNavigation, ResourceList, TheHeader, NewResource},
  data() {
    return {
      activeComponent: 'resource-list',
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
  provide() {
    return {
      resources: this.resources,
      onResourceAdded: this.onResourceAdded
    }
  },
  methods: {
    onResourceAdded(newResource) {
      const resource = {
        id: generateId(),
        ...newResource,
        isFinished: false
      };

      this.resources.push(resource);
    },
    onTabClicked(tab) {
      this.activeComponent = tab;
    }
  }
};
</script>

<style>
:root {
  --c-primary: #DFBAC1;
  --c-primary-dark: #B5A5BF;
  --c-primary-neutral: #D8CCE0;
  --c-neutral: #757da4;
  --c-black: #13161F;
  --c-black-light: #33394F;
  --basic-transition: 0.2s ease-in-out;
  --basic-box-shadow: 0 2px 6px 0 rgba(117, 125, 164, 0.3);
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

a {
  color: inherit;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

.main {
  padding: 20px;
}
</style>
