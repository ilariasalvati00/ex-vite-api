<script setup>
import axios from 'axios'
let keyword = ""

function search() {
    return;
}
</script>

<template>
    <input type="text" v-model="keyword">
    <button @click="search()">Cerca</button>
</template>

<style scoped></style>