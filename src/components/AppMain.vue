<script>
import {store} from "../store";
import AppCardTv from "./AppCardTv.vue";
import AppCardMovie from "./AppCardMovie.vue";
export default {
    components: {
        AppCardMovie,
        AppCardTv,

    },
    data () {
        return {
            store,
        }
    },

}
</script>




<template>
    <div class="container">
        <div class="row row-cols-4">
            <div class="col" v-show="curMovie.poster_path" v-for="curMovie in store.moviesArray">
                <AppCardMovie :cardsobjMovie="curMovie"/>

            </div>
        </div>
    </div>

    <div class="container my-5">
        <div class="row row-cols-4">
            
            <div class="col" v-show="curTv.poster_path" v-for="curTv in store.tvArray">
                <AppCardTv :cardsObj="curTv"/>
            </div>

        </div>
    </div>

</template>


<style scoped lang="scss">

</style>