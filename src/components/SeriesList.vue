<template>
  <section class="pt-2">
      <h6 v-for="serieTV in seriesTV" :key="serieTV.id">
            <i v-for="(vote,index) in intnum(serieTV.vote_average)" class="fa-solid fa-star ms_gold" :key="index"></i>
            <i v-for="(star,i) in (5 - intnum(serieTV.vote_average)) " class="fa-regular fa-star" :key="i"></i>
            {{serieTV.name}} - {{serieTV.original_name}} 
             <div v-for="(language,counter) in languages" :key="counter">
                  <img v-if="languages.includes(serieTV.original_language)" :src="require(`../assets/img/${language}`)">
            
                  <h6 v-else>{{serieTV.original_language}}</h6>
             </div>
            
             
               
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
      languages: ['en', 'de', 'es', 'fr', 'ja', 'it']
    };
  },
 methods: {
    intnum(number){
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