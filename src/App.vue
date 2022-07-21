<template>
  <div id="app">
    <Header @search="searching"/>
    <Main v-for="film in films" :key="film.id" :search="film" />
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
      searchinput:"",
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
          console.log(this.films)
        });
    },

    searching(ago){
      console.log(ago);
      this.searchinput=ago;
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

<style lang="scss">
#app {
  @import "~bootstrap/scss/bootstrap.scss";
}
</style>
