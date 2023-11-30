<script >

import axios from 'axios'; /* importo axios */
import Names from './components/Names.vue';
import Search from './components/Search.vue'

export default {
  components: {
    Names,
    Search,
  },
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

  },
}

</script>

<template>
  <Search :informations="dati"></Search>
  <Names :informations="dati"></Names>
</template>

<style scoped></style>
