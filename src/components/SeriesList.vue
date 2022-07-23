<template>
  <section class="pt-4">
      <h6 v-for="serieTV in seriesTV" :key="serieTV.id">
         <h2>Serie TV</h2>
         <i v-for="(vote,index) in getstars(serieTV.vote_average)" class="fa-solid fa-star ms_gold" :key="index"></i>
         <i v-for="(star,i) in (5 - getstars(serieTV.vote_average)) " class="fa-regular fa-star" :key="i"></i>
         {{serieTV.name}} - {{serieTV.original_name}} 
         <img class="ms_width" v-if="languages.includes(serieTV.original_language)" :src="require(`../assets/img/${serieTV.original_language}.png`)">
         <span v-else>{{serieTV.original_language}}</span>
         <img :src="(`https://image.tmdb.org/t/p/w342${serieTV.poster_path}`)" :alt="serieTV.title" class="ms_width_img pt-2 pb-4">
      </h6>
   </section>
</template>

<script>
export default {
 name: 'SeriesList',
 props: ['seriesTV'],

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


.ms_gold{
   color: gold;
}

</style>