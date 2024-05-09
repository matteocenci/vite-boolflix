<script>

    export default {
        props: {
            cardsobjMovie: Object
        },

        computed: {
            title () {
                return this.cardsobjMovie.original_title
            }
        }
    }
</script>

<template>
    <img :src="`https://image.tmdb.org/t/p/w342${cardsobjMovie.poster_path}`" alt="">
</template>