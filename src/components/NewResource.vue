<template>
  <form @submit.prevent="onSubmit">
    <ul>
      <li>
        <app-input>
          <label for="1">Name</label>
          <input id="1" type="text" v-model="resourceName">
        </app-input>
      </li>
    </ul>
    <app-button type="submit">Add New</app-button>
  </form>
</template>

<script>
import AppButton from '@/components/UI/AppButton';
import AppInput from '@/components/UI/AppInput';
export default {
  name: 'new-resource',
  components: {AppInput, AppButton},
  emits: ['resource-added'],
  data() {
    return {
      resourceName: ''
    };
  },
  methods: {
    onSubmit() {
      this.$emit('resource-added', this.resourceName);
    }
  }
}
</script>

<style>

</style>
