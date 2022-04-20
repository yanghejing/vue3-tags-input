<template>
  <div id="app">
    <div class="form">
      <!--      npm publish-->
      <vue3-tags-input placeholder="add tags"
                       :limit="2"
                       :tags="tags"
                       :validate="csValidate"
                       @on-focus="handleFocus"
                       @on-blur="handleBlur"
                       @on-remove="handleRemove"
                       @on-tags-changed="handleChangeTag">
        <template #item="{ name, index }">
          {{ name }}
        </template>
      </vue3-tags-input>
      <br>
      <div class="custom-input-tags">
        <vue3-tags-input :tags="tags"
                         v-model="tag"
                         placeholder="custom input tags" />
        <input type="text" v-model="tag">
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import Vue3TagsInput from '@/vue3-tags-input.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    Vue3TagsInput
  },
  data() {
    return {
      tag: 'model',
      tags: ['VUE', 'HTML', 'CSS']
    }
  },
  methods: {
    handleChangeTag(tags) {
      this.tags = tags;
    },
    csValidate(value) {
      const regex = new RegExp(/^[a-zA-Z]+$/);
      return regex.test(value)
    },
    handleFocus(event) {
      console.log('focus', event)
    },
    handleBlur(event) {
      console.log('blur', event)
    },
    handleRemove(index) {
      console.log('on remove', index)
    },
  }
});
</script>

<style>
body {
  font-family: Inter var,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;
}
.form {
  width: 450px;
}
</style>
