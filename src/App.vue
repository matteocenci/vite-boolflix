<script>


import axios from "axios";
import {store} from "./store";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";




export default {
  components: {
    AppHeader,
    AppMain
  },

  data() {
    return{
      store,
    };
  },
  created () {
    
  },
  methods: {

    getFilms() {
      const paramsobj = {
        api_key: this.store.apiKey,
        query: this.store.searchQuery,
      }
      axios.get(" https://api.themoviedb.org/3/search/tv", {
      params: paramsobj
    })
    .then((resp) => {
      
      this.store.tvArray = resp.data.results;
    });
    axios.get(" https://api.themoviedb.org/3/search/movie", {
      params: paramsobj
    })
    .then((resp) => {
      
      this.store.moviesArray = resp.data.results;
      console.log(this.store.moviesArray);
    });
    }
  }
}

</script>

<template>
  <AppHeader @search = "getFilms"/>
  <AppMain/>

</template>

<style scoped>
* {
  background-color: lightgray;
}


</style>
