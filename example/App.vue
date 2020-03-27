<template>
  <section class="container">
    <div class="mb-2"><toggle-selector v-model="value1"/> value1: {{value1}}</div>
    <div class="mb-2"><toggle-selector v-model="value2" left_text="〇" right_text="×"/> value2: {{value2}}</div>
    <div class="mb-2"><toggle-selector v-model="value3" left_text="半" right_text="丁"/> value3: {{value3}}</div>
    <div class="mb-2"><toggle-selector v-model="value4" :options="options" button_width="4rem"/> value4: {{value4}}</div>
  </section>
</template>

<style lang="scss" scoped>
</style>

<script>
import ToggleSelector from '../src/vue-mg-toggle-selector'
import 'bootstrap/dist/css/bootstrap.min.css'
export default {
  data() {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      options: [
        { name: 'OK', btnColor: 'primary' },
        { name: 'NG', btnColor: 'danger' },
        { name: '-', btnColor: 'dark' },
      ],
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