<script >

import axios from 'axios'; /* importo axios */
export default {
  data() {
    return {
      dati: []
    }
  },
  mounted() {
    this.ServerInfo()
  },
  methods: {
    ServerInfo() {
      axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10").then(risultato => {
        this.dati = risultato.data
        console.log(this.dati)
      })
    },
    info(dati) {
    }
  }
}
</script>

<template>
  <div class="box">
    <div v-for="dato in dati" @click="info()">{{ dato.name }}</div>
  </div>
</template>

<style scoped>
.box {
  padding: 30px;
  border: 1px solid white;
}
</style>
