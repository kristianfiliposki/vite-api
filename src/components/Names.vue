<script>
import axios from 'axios'; /* importo axios */
import { store } from '../store.js'
export default {
    name: "Names",
    data() {
        return {
            store
        }
    },
    mounted() {
        console.log(this.store)

    }
}
</script>
<template>
    <div>
        <div class="box">
            <div class="pub" v-for="info in store.dati">
                <div>
                    {{ info.name }}
                </div>
                <div class="cap">
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