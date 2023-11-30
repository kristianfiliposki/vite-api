<script>
import Search from './Search.vue';
export default {
    name: "Names",
    props: ["informations", "Cap"],
}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <div class="pub" :class='{ hidden: (nomi == false) }' v-for="info in informations">{{ info.name }}</div>
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

.hidden {
    display: none;
}
</style>