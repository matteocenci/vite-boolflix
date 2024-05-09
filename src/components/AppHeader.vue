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
    <h1 class="text-left mt-2 px-4 fw-bold"> BoolFlix </h1>
    <div class="container py-5">
        <div class="d-flex justify-content-left">
            <input  v-model="store.searchQuery" id="search" placeholder="ex. Transformers">
            <button @click="$emit('search')" class="button mx-3">Invia</button>
            
        </div>
    </div>

</template>

<style scoped lang="scss">
.button {
    padding: 5px;
}
</style>