<template>
  <div>
    <h1>Country List</h1>
      <div class="">
        <country-detail :country="selectedCountry" ></country-detail>
          <countries-list :countries='countries'>

          </countries-list>
      </div>

  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
import CountryDetail from './components/CountryDetail.vue'
import { eventBus } from './main.js'


export default {
  name: 'app',
  data(){
    return {
      countries: [
        // {name: 'Scotland', visited: true},
        // {name: 'Scotland2', visited: false},
        // {name: 'Scotland3', visited: true}
      ],
      selectedCountry: null
    }
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country
    })

  },
  components: {
    'country-detail': CountryDetail,
    'countries-list': CountriesList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
