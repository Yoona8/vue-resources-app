<template>
  <nav class="tabs">
    <ul class="tabs__list">
      <li class="tabs__item">
        <a
          class="tabs__link"
          :class="resourceListTabMode"
          @click.prevent="onTabClick('resource-list')"
          href="#"
        >Resources</a>
      </li>
      <li class="tabs__item">
        <a
          class="tabs__link"
          :class="newResourceTabMode"
          @click.prevent="onTabClick('new-resource')"
          href="#"
        >Add New</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'tabs-navigation',
  emits: ['tab-clicked'],
  data() {
    return {
      currentTab: 'resource-list'
    }
  },
  computed: {
    resourceListTabMode() {
      return {'tabs__link--current': this.currentTab === 'resource-list'};
    },
    newResourceTabMode() {
      return {'tabs__link--current': this.currentTab === 'new-resource'};
    }
  },
  methods: {
    onTabClick(tab) {
      this.currentTab = tab;
      this.$emit('tab-clicked', tab);
    }
  }
}
</script>

<style scoped>
.tabs {
  max-width: 1280px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}

.tabs__list {
  display: flex;
  margin: 0;
  padding: 0;
  list-style: none;
}
</style>
