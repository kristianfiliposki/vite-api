<script>
import axios from 'axios';
export default {
    name: "Names",
    props: ["informations"],
}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <div class="pub" v-for="info in informations">{{ info.name }}</div>
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