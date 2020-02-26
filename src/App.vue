<template>
  <div id="#app">
    <h1 class="title">Country List</h1>
    <div class="container">
      <country-detail :country='selectedCountry'></country-detail>
      <countries-list :countries='countries'></countries-list>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountryDetail from './components/CountryDetail.vue';
import {eventBus} from './main.js'

export default {
  name: 'App',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  },
  mounted(){
   fetch('https://restcountries.eu/rest/v2/all')
   .then(res => res.json())
   .then(countries => this.countries = countries)

   eventBus.$on('country-selected', (country) =>{
     this.selectedCountry = country;
   })
  }
}

</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: pink;
}

h1.title {
  font-size: 4em;
  padding: 1em 0em;

}
</style>
