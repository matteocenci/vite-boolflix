<script>
import {store} from "../store";
import AppCard from "./AppCard.vue";


export default {
    components: {
        AppCard,
        

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
        <h3>Movies</h3>
        <div class="row row-cols-4">
            <div class="col my-2" v-show="curMovie.poster_path" v-for="curMovie in store.moviesArray">
                <AppCard :cardsObj="curMovie"/>

            </div>
        </div>
    </div>

    <div class="container my-5">
        <h3>Tv Series</h3>
        <div class="row row-cols-5 gx-4">
            
            <div class="col my-3" v-show="curTv.poster_path" v-for="curTv in store.tvArray">
                <AppCard :cardsObj="curTv"/>
            </div>

        </div>
    </div>

</template>


<style scoped lang="scss">
.container {
    h3 {
        font-weight: 600;
    }
}
.col {
    max-width: calc(100% / 5 - 40px / 5);
    
    
    flex-wrap: nowrap;
    
}

</style>