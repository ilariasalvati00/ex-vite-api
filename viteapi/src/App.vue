<script setup>
import axios from 'axios'
import FilterAPI from './components/FilterAPI.vue'
import Brewery from "./components/Brewery.vue"

const api_path = "https://api.openbrewerydb.org/v1/breweries?by_country=poland&per_page=10"
let done = false;
let breweries_list = [];

axios.get(api_path).then((risposta) => {
  breweries_list = risposta.data;
  done = true;
  console.log(done);
})
</script>

<template v-if="done==false">
  <p>Loading...</p>
</template>

<template v-else>
  <div>
    <Brewery v-for="(birreria) in breweries_list" :nome="birreria.name" :citta="birreria.city"
      :provincia="birreria.state_province" :indirizzo="birreria.street" :stato="birreria.country"></Brewery>
  </div>
</template>

<style scoped></style>
