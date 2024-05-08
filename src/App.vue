<script>
import axios from "axios";
import {store} from "./store";
export default {
  data() {
    return{
      store,
    };
  },
  created () {
    axios.get(" https://api.themoviedb.org/3/search/tv?api_key=b2ead90c1236f96f4b0e9528732a8bfc", {
      params: {
        api_key: this.store.apiKey,
        query: "Ciao"
        
        
      },
    })
    .then((resp) => {
      console.log(resp);
    });
  }
}

</script>

<template>

</template>

<style>


</style>
