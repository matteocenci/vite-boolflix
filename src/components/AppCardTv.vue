<script>


export default {
    props: {
        cardsObj: Object
    },
    computed: {
        title() {
            return this.cardsObj.original_name
        }
    }
    

    

}
</script>


<template>
    <img :src="`https://image.tmdb.org/t/p/w342${cardsObj.poster_path}`" alt="">
    <p>{{ title }}</p>
    

</template>