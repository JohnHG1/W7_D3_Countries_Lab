<template lang="html">
<div class="country-detail"v-if="country">
  <h3>{{country.name}}</h3>
  <p><b>Population:</b> {{country.population}}</p>
  <p><b>Capital:</b> {{country.capital}}</p>
  <img :src="country.flag" alt="">




</div>

</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>

img {
  /* width: inherit; */
  width: 10em;
}

.country-detail {
  text-align: right;
  border: 1.2px dotted;
  border-radius: 2em;
  width: 25%;
  position: fixed;
  right: 0;
  padding: 1.6em 2em 1.6em 1em;
  background-color: gold;
  font-size: 1.5em;
  margin-right: 1em;
}

h3 {
  font-size: 1.3em;
  text-decoration: underline;
  padding-bottom: 0.5em;
}
</style>
