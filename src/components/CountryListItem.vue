<template lang="html">
  <option v-on:change="handleChange">{{country.name}}</option>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'country-list-item',
  props: ['country'],
  methods: {
    handleChange: function () {
      eventBus.$emit('country-selected', this.country);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
