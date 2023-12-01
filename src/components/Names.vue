<script>
export default {
    name: "Names",
    props: ["informations", "caps"],
    data() {
        return {
            isVisible: false
        }
    },
    methods: {
        toggleVisibility() {
            this.isVisible = !this.isVisible;
        }
    }

}
</script>
<template>
    <div>
        <div class="box">
            <h1>Where is yor Pub?</h1>
            <div class="pub" v-for="info in informations">
                <div>
                    <button @click="toggleVisibility">
                        {{ info.name }}
                    </button>
                </div>
                <div v-show="isVisible" class="cap">
                    {{ info.postal_code }}
                </div>

            </div>
        </div>
        <div>
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

.cap font-weight: 900;
}

.hidden {
    display: none;
}
</style>