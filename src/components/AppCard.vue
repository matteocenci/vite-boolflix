<script>


export default {
    data() {
        return {
            flagArray: ["en","es","fr","it"]
        }
    },
    props: {
        cardsObj: Object
    },
    computed: {
        originalTitle() {
            if (this.cardsObj.original_name) {
                return this.cardsObj.original_name

            } else {
                return this.cardsObj.original_title
            }
        },
        valutation() {
            const vote = Math.round(this.cardsObj.vote_average / 2);
            return vote
        },
        Title() {
            if (this.cardsObj.name) {
                return this.cardsObj.name
            } else {
                return this.cardsObj.title
            }
        },
        Description() {
            return this.cardsObj.overview
        }

    },
    methods: {
        getImage(value) {
            if (this.flagArray.includes(value)) {
                return new URL(`../assets/img/${value}.jpg`, import.meta.url).href; 
            } else {
                return new URL(`../assets/img/unknown.jpg`, import.meta.url).href;
            }
            
    
        }

    }
    

    

}
</script>


<template>
    <div class="containercard">
        <div class="cardfront">
            <img :src="`https://image.tmdb.org/t/p/w342${cardsObj.poster_path}`" alt="">
    
        </div>
        <div class="backcard">
            <img :src="getImage(cardsObj.original_language)" alt="">
            <div class="title"><strong>Title:</strong> {{ Title }}</div>
            <div class="ori-title"><strong>Original Title:</strong> {{ originalTitle }}</div>
            <div class="containerdescr">
                <div class="descr">
                    <strong>Overview:</strong> {{ Description }}
                </div>
                
            </div>
            <div class="vote">
                <span v-for="vote in valutation">
                    <i class="fa-solid fa-star"></i>
                </span>
                <span v-for="vote in 5-valutation">
                    <i class="fa-regular fa-star"></i>
                </span>
                    

            </div>
    
        </div>

    </div>
    

</template>

<style scoped lang="scss">
.containercard {
    position: relative;
    width: 100%;
    height: 100%;
    .cardfront {
        transition: 2s;
        transform-style: preserve-3d;
        width: 100%;
        height: 100%;
        img {
            border-radius: 10px;
            width: 100%;
            height: 100%;
        }
    }

    .backcard {
        transition: 2s;
        transform: rotateY(180deg) ;
        transform-style: preserve-3d;
        border-radius: 10px;
        background-color: lightcoral;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;

        img {
            width: 20%;
            height: 10%;
            margin: 5px;
        }

        .containerdescr {
            
            .descr {
                display: -webkit-box; 
                -webkit-box-orient: vertical; 
                -webkit-line-clamp: 4; 
                overflow: hidden; 
                text-overflow: ellipsis; 
            }
        }
        
        opacity: 0;
        .vote{
            display: flex;
            flex-direction: row;
            position: absolute;
            bottom: 0;
            right: 0;
        }
    }

    &:hover {
        

        .cardfront{
            transition: 2s;
            transform: rotateY(180deg);
            opacity: 0;

        }
        .backcard {
            transition: 2s;
            transform: rotateY(360deg);
            opacity: 1;
        }
    }

    
}
</style>