<script>
export default {
    name: "Names",
    props: ["informations",],
    data() {
        return {
            isVisible: false,
            testo: "",
            find: false,
        }
    },

    methods: {
        filter() {
            for (let i = 0; i < this.informations.length; i++) {
                let info = this.informations[i];
                if (info.postal_code.includes(this.testo)) {
                    this.find = true
                    console.log((this.find))
                    console.log(info)
                }
                else {
                    this.find = false

                }
                info.push(this.find);
            }
        },
    }

}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <input type="text" v-model="testo" @keyup="filter()">
            <div class="pub" v-for="info in informations">
                <button>
                    {{ info.name }}
                </button>
                <div v-if="find" class="cap">
                    {{ info.postal_code }}
                </div>
            </div>
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
    display: flex;
}

.cap {
    font-weight: 900;
    margin-left: 20px;
    display: flex;
    align-items: center;
}

.hidden {
    display: none;
}
</style>