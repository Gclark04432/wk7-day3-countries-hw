<template lang="html">
  <select>
    <country-list-item v-for="(country, index) of countries-list" :country="country" :key="index"></country-list-item>
  </select>
</template>

<script>
import CountryListItem from './CountryListItem.vue';

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "country-list-item": CountryListItem
  }
}
</script>

<style lang="css" scoped>
</style>
