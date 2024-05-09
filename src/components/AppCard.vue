<script>


export default {
    props: {
        cardsObj: Object
    },
    computed: {
        title() {
            if (this.cardsObj.original_name) {
                return this.cardsObj.original_name

            } else {
                return this.cardsObj.original_title
            }
        }
    }
    

    

}
</script>


<template>
    <div class="card">
        <img :src="`https://image.tmdb.org/t/p/w342${cardsObj.poster_path}`" alt="">

    </div>
    <!-- <p>{{ title }}</p> -->
    

</template>

<style scoped lang="scss">
.card {
    width: 100%;
    height: 100%;

    img {
        width: 100%;
        height: 100%;
    }
}
</style>