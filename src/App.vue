<template lang="html">
  <div>
    <select>
      <option v-for="country in countriesList">{{ country.name }}</option>
    </select>
  </div>
</template>

<script>
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
  }
}
</script>

<style lang="css" scoped>
</style>
