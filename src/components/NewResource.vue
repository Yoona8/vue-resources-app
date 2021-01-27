<template>
  <app-card>
    <form class="new" @submit.prevent="onSubmit">
      <ul class="new__fields">
        <li class="new__field">
          <app-input>
            <label for="new-name">Name</label>
            <input
              id="new-name"
              name="new-name"
              type="text"
              v-model="name"
            >
          </app-input>
        </li>
        <li class="new__field">
          <app-input>
            <label for="new-description">Description</label>
            <textarea
              id="new-description"
              name="new-description"
              v-model="description"
            ></textarea>
          </app-input>
        </li>
        <li class="new__field">
          <app-input>
            <label for="new-tag">Tag</label>
            <select
              id="new-tag"
              name="new-tag"
              v-model="tag"
            >
              <option>JavaScript</option>
            </select>
          </app-input>
        </li>
        <li class="new__field">
          <app-input>
            <label for="new-url">Url</label>
            <input id="new-url" name="new-url" type="url">
          </app-input>
        </li>
      </ul>
      <app-button
        type="submit"
      >Add New</app-button>
    </form>
  </app-card>
</template>

<script>
import AppButton from '@/components/UI/AppButton';
import AppInput from '@/components/UI/AppInput';
import AppCard from '@/components/UI/AppCard';

export default {
  name: 'new-resource',
  components: {AppCard, AppInput, AppButton},
  inject: ['onResourceAdded'],
  data() {
    return {
      name: '',
      description: '',
      tag: '',
      url: ''
    };
  },
  methods: {
    onSubmit() {
      const resource = {
        name: this.name,
        description: this.description,
        tag: this.tag,
        url: this.url
      };

      this.onResourceAdded(resource);
    }
  }
}
</script>

<style>

</style>
