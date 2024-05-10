<script>
import {store} from "../store.js";

export default {
    emits: ['search'],
    data () {
        return {
            store,
        }
    }

}
</script>


<template>
    <div class="title">
        <h1 class="text-left px-4 fw-bold"> BoolFlix </h1>

    </div>
    <div class="container py-5">
        <div class="d-flex justify-content-left">
            <input  v-model="store.searchQuery" id="search" placeholder="ex. Transformers">
            <button @click="$emit('search')" class="button mx-3">Invia</button>
            
        </div>
    </div>

</template>

<style scoped lang="scss">
.title {
    background-color: #15110E;
    margin: 0;
    h1 {
        color: #FB1B25;
    }
}
.button {
    padding: 5px;
}
</style>