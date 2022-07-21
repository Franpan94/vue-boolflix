<template>
  <div id="app">
    <Header @search="searching"/>
    <div v-if="filterfilms.length > 0">
      <Main v-for="film in filterfilms" :key="film.id" :film="film" />
    </div>
    <div v-else>
      <h2>Nessun risultato trovato</h2>
    </div>
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
      films: [],
      filterfilms: [],
    };
  },

  methods:{
    getfilm() {
      axios
        .get("http://api.themoviedb.org/3/search/movie?api_key=db8eb2464e37ce0450116e6ea6d513f3&query=return")
        .then((results) => {
          this.films = results.data.results;
          this.filterfilms=this.films;
        })
      },

    searching(word){
      if(word === ''){
        this.filterfilms = this.films;
      } else{
         this.filterfilms = this.films.filter((film) => film.title.toLowerCase().includes(word));
      }
      
    }
  },

  created() {
    this.getfilm();
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
