<script >

import axios from 'axios'; /* importo axios */
import Names from './components/Names.vue';
import Search from './components/Search.vue'
import { store } from './store.js'

export default {
  components: {
    Names,
    Search,
  },
  data() {
    return {
      store,


    };
  },
  mounted() {
    this.ServerInfo();

  },
  methods: {
    ServerInfo() {
      /* se store testo è vuoto allora... */
      axios.get("https://api.openbrewerydb.org/v1/breweries?by_postal").then(risultato => {
        this.store.dati = risultato.data;
        console.log(this.store.dati);
      });

    },
    filter() {
      /* se non è vuoto allora... */
      axios.get(`https://api.openbrewerydb.org/v1/breweries?by_postal=${this.store.testo}`).then(risultato => {
        this.store.dati = risultato.data;
        console.log(risultato.data);
      })


    },
  }
}
</script>

<template>
  <Search @ricerca="filter()" />
  <Names />
</template>

<style scoped></style>
