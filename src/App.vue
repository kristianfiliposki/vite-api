<script >

import axios from 'axios'; /* importo axios */
import Names from './components/Names.vue';

export default {
  components: {
    Names,
  },
  data() {
    return {
      dati: [],
      caps: ["info.postal_code"],


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
  <Names :informations="dati" :caps="caps"></Names>
</template>

<style scoped></style>
