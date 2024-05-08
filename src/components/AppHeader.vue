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
    <h1 class="text-center mt-2 fw-bold"> BoolFLix </h1>
    <div class="container py-3">
        <div class="d-flex justify-content-between">
            <input  v-model="store.searchQuery" id="search">
            <button @click="$emit('search')">Invia</button>
            <label for="search">
                Cerca un film
            
            </label>
        </div>
    </div>

</template>

<style scoped lang="scss">
</style>