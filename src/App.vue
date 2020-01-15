<template lang="html">

</template>

<script>
export default {
  name: 'app',
  data: function () {
    return {
      countriesList: []
    }
  },
  mounted: function () {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(result => result.json())
    .then(countries => this.countriesList = countries)
  }
}
</script>

<style lang="css" scoped>
</style>
