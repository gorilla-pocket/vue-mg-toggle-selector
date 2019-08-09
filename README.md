# vue-mg-toggle-selector

![npm](https://img.shields.io/npm/v/vue-mg-toggle-selector)
![npm](https://img.shields.io/npm/dm/vue-mg-toggle-selector)

## Installation

```
npm i vue-mg-toggle-selector
```

## Usage

app.js

```javascript
import ToggleSelector from 'vue-mg-toggle-selector'
Vue.component('ToggleSelector', ToggleSelector)
```

Example:

```html
<template>
  <section class="container">
    <toggle-selector v-model="value1"/> value1: {{value1}}
    <toggle-selector v-model="value2" left_text="〇" right_text="×"/> value2: {{value2}}
    <toggle-selector v-model="value3" left_text="半" right_text="丁"/> value3: {{value3}}
  </section>
</template>

<style lang="scss" scoped>
</style>

<script>
import ToggleSelector from '../src/vue-mg-toggle-selector'
export default {
  data() {
    return {
      value1: '',
      value2: '',
      value3: '',
    }
  },
    methods: {
      //
    },
  components: {
    ToggleSelector,
  },  
}
</script>
```

## License

MIT
