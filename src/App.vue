<template>
  <div id="app">
    <Header @search="getfilmsandseriesTV"/>
    <Main :films = films :seriesTV = seriesTV />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from "axios"

export default {
  name: 'App',

  data: function () {
    return {
      apikey: 'db8eb2464e37ce0450116e6ea6d513f3',
      apiurlfilms: 'https://api.themoviedb.org/3/search/movie',
      films: [],
      seriesTV: [],
      apiurlseriesTV: 'https://api.themoviedb.org/3/search/tv',
    };
  },

  methods:{
    getfilmsandseriesTV(word) {
      axios
        .get(`${this.apiurlfilms}?api_key=${this.apikey}&query=${word}&language=it-IT`)
        .then((result) => {
        this.films = result.data.results;
        })
        axios
        .get(`${this.apiurlseriesTV}?api_key=${this.apikey}&query=${word}&language=it-IT`)
        .then((result) => {
        this.seriesTV = result.data.results;
        console.log(this.seriesTV);
        })
      },
  },
  
  components: {
    Header,
    Main,
  }
}
</script>

<style lang ="scss">
#app {
  @import "~bootstrap/scss/bootstrap.scss";
}
</style>
