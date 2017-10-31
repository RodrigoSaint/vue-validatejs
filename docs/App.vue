<template>
  <div class="docs">
    <input type="text" v-model="model.name" placeholder="Name">
    <vue-validate :model="model" :validation="validation" property-name="name"></vue-validate>
  </div>
</template>

<script>
  import VueValidate from '../src/vue-validate.js.vue'

  export default {
    name: 'App',
    components: { VueValidate },

    data () {
      return { model: {}, validation: {name: {presence: {allowEmpty: false}}} }
    }
  }
</script>

<style lang="scss">
  .docs {
    width: 50%;
    margin: auto;
    padding: 10px;
  }

  .error-message {
    color: red;
  }
</style>
