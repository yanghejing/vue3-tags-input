# vue3-tags-input

A tags input component for Vue 3 with custom validation, templating...

[Demo & Docs](https://vue3-tags-input.netlify.app)

# Install

```
npm i vue3-tags-input
```

# Usage

```html
<template>
    <vue3-tags-input :tags="tags"
                     placeholder="input tags" />
</template>
```

```javascript
<script>
    import { defineComponent } from 'vue';
    import Vue3TagsInput from 'vue3-tags-input';

    export default defineComponent({
    components: {
        Vue3TagsInput
    },

    data() {
        return {
            tags: ['VUE', 'HTML', 'CSS']
        }
    },
})
</script>
```

# License 

## [MIT](https://vue3-tags-input.netlify.app)

Copyright (c) 2022 Chinh Pham Duc (chinh12hy@gmail.com)
