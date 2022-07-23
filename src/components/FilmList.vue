<template>
  <section class="pt-4">
    <h6 v-for="film in films" :key="film.id">
      <h2>Film</h2>
      <i v-for="(vote,index) in getstars(film.vote_average)" class="fa-solid fa-star ms_gold" :key="index"></i>
      <i v-for="(star,i) in (5 - getstars(film.vote_average)) " class="fa-regular fa-star" :key="i"></i>
      {{film.title}} - {{film.original_title}} 
      <img v-if="languages.includes(film.original_language)" :src="require(`../assets/img/${film.original_language}.png`)" :alt="film.title" class="ms_width">
      <h6 v-else>{{film.original_language}}</h6>
      <img :src="(`https://image.tmdb.org/t/p/w342${film.poster_path}`)" :alt="film.title" class="ms_width_img pt-2 pb-4">
    </h6>
    
  </section>
</template>

<script>
export default {
  name: 'FilmList',
  props: ['films'],

  data: function () {
    return {
      languages: ['en', 'de', 'es', 'fr', 'japan', 'it']
    };
  },
 methods: {
    getstars(number){
       return Math.round(number/2);
    }
 }
}
</script>

<style lang ="scss">
   .ms_width{
    width: 25px;
   }

   .ms_width_img{
    width: 150px;
    display: block;
   }
</style>