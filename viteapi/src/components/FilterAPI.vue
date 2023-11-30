<script>
import axios from 'axios'

export default {
    components: {

    },
    data() {
        return {
            keyword: ""
        };
    },
    methods: {
        search: function () {
            console.log(this.keyword);
        }
    },
}

</script>

<template>
    <input type="text" v-model="keyword">
    <button @click="search()">Cerca</button>
</template>

<style scoped></style>