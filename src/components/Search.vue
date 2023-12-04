<script>
import axios from 'axios'; /* importo axios */
import { store } from '../store.js'
export default {
    name: "Search",
    data() {
        return {
            store
        }
    },

    methods: {

        filter() {
            /*             axios.get(`https://api.openbrewerydb.org/v1/breweries?by_postal=${this.testo}`).then(risultato => {
                            this.store.dati = risultato.data;
                            console.log(risultato.data);
                        }); */
            this.$emit("ricerca")
        }
    },


}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <input type="text" v-model="store.testo" @keyup="filter()">
        </div>
    </div>
</template>
<style scoped>
.box {
    padding: 30px;
    border: 1px solid white;
}
</style>