<template lang="html">
  <div>
    <select>
      <countries-list :country="country"></countries-list>
    </select>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import CountryList from './components/CountryList.vue';

export default {
  name: 'app',
  data: function () {
    return {
      countriesList: [],
      selectedCountry: null
    }
  },
  mounted: function () {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(result => result.json())
    .then(countries => this.countriesList = countries);

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    });
  },
  components: {
  "countries-list": CountryList,
}
}
</script>

<style lang="css" scoped>
</style>
