<script>
export default {
    name: "Search",
    props: ["informations", "Cap"],
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
                if (element.postal_code.includes(this.Pub)) {
                    console.log("done");
                    this.nomi = (element.postal_code.includes(this.Pub));
                    this.nomi = true;

                }
                else {
                    this.nomi = false;

                }
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
            <div></div>
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