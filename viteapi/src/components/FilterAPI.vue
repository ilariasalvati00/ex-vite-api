<script>
import axios from 'axios'
import Brewery from "./Brewery.vue"

const api_search = "https://api.openbrewerydb.org/v1/breweries/search?&per_page=10&query="

export default {
    emits: ['update:search_loaded'],
    components: {
        Brewery
    },
    data() {
        return {
            keyword: "",
            searched_breweries: []
        };
    },
    methods: {
        search: function () {
            axios.get(api_search + this.keyword).then((risposta) => {
                this.searched_breweries = risposta.data;
                this.$emit('update:search_loaded')
            });
        }
    },
}

</script>

<template>
    <input type="text" v-model="keyword" @keyup.enter="search()">
    <button @click="search()">Cerca</button>
    <Brewery v-for="(birreria) in searched_breweries" :nome="birreria.name" :citta="birreria.city"
        :provincia="birreria.state_province" :indirizzo="birreria.street" :stato="birreria.country"
        :tipo="birreria.brewery_type"></Brewery>
</template>

<style scoped></style>