<script>

export default {
    components: {

    },
    data() {
        return {};
    },
    methods: {},
    props: ({
        nome: String,
        citta: String,
        provincia: String,
        indirizzo: String,
        stato: String,
        tipo: String
    })
}


</script>

<template>
    <div class="card">
        <div class="col">
            <b>{{ nome }}</b>
        </div>
        <div class="col">
            <p>{{ indirizzo }} - {{ citta }} - {{ provincia }} - {{ stato }}</p>
        </div>
        <div class="col">
            <p>{{ tipo }}</p>
        </div>
    </div>
</template>


<style scoped>
.card {
    display: flex;
    flex-direction: row;
    border: 1px solid black;
}

.col {
    display: flex;
    flex: 1 1 calc(100% / 3);
}
</style>