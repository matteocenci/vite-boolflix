<script>
import {store} from "../store";
import AppCardTv from "./AppCardTv.vue";
export default {
    components: {
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

            <div class="col" v-show="curTv.poster_path" v-for="curTv in store.tvArray">
                <AppCardTv :cardsObj="curTv"/>
            </div>
        </div>
    </div>

</template>


<style scoped lang="scss">

</style>