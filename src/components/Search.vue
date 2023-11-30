<script>
export default {
    name: "Search",
    props: ["informations"],
    data() {
        return {
            Pub: ""
        }

    },
    mounted() {
    },
    methods: {
        filter() {
            this.informations.forEach(element => {
                if (element.name.includes(this.Pub)) {
                    console.log("done")

                }
                else { console.log("male") }
            });
        }
    }
}
</script>

<template>
    <div class="container">
        <div>
            <input type="text" v-model=Pub>
            <button @click="filter(this.Pub, this.informations)"></button>
            <div>{{ informations }}</div>
        </div>


    </div>
</template>

<style scoped>
.container {
    display: flex;
    margin: 2em;
    width: 100%;
}

input {
    margin-right: 20px;
}
</style>