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
        <div class="row row-cols-4">
            <div class="col my-2" v-show="curMovie.poster_path" v-for="curMovie in store.moviesArray">
                <AppCard :cardsObj="curMovie"/>

            </div>
        </div>
    </div>

    <div class="container my-5">
        <div class="row row-cols-5 gx-4">
            
            <div class="col my-3" v-show="curTv.poster_path" v-for="curTv in store.tvArray">
                <AppCard :cardsObj="curTv"/>
            </div>

        </div>
    </div>

</template>


<style scoped lang="scss">
.col {
    max-width: calc(100% / 5 - 40px / 5);
    
    
    flex-wrap: nowrap;
    
}

</style>