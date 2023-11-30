<script>
import axios from 'axios';
export default {
    name: "Names",
    data() {
        return {
            dati: []
        };
    },
    mounted() {
        this.ServerInfo();
    },
    methods: {
        ServerInfo() {
            axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10").then(risultato => {
                this.dati = risultato.data;
                console.log(this.dati);
            });
        },
        info(dati) {
        }
    },
}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <div class="pub" v-for="dato in dati">{{ dato.name }}</div>
        </div>
    </div>
</template>
<style scoped>
.box {
    padding: 30px;
    border: 1px solid white;
}

.pub {
    margin: 2em;
    font-size: 1.4em;
}
</style>