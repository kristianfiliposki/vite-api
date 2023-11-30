<script >
import axios from 'axios'; /* importo axios */
export default {
  data() {
    return {

    }
  },
  mounted() {
    axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=scotland&per_page=10").then(risultato => {
      console.log(risultato)
    })
  }
}
</script>

<template>
  <div>dsanjksnj</div>
</template>

<style scoped></style>
