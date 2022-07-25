<template>
  <section class="pt-4 row">
    <h1 class="pt-5 ms_color">Lista SerieTV</h1>
    <div v-for="serieTV in seriesTV" :key="serieTV.id" class="col-3">
         <h2>{{ serieTV.name }}</h2> 
         <img
           :src="`https://image.tmdb.org/t/p/w342${serieTV.poster_path}`"
           :alt="serieTV.name"
           class="ms_width_img pt-2 pb-4"
         />
         <div class="ms_bg_black p-2 ms_none">
           <h2>{{ serieTV.original_name }}</h2>
           <img
             class="ms_width"
             v-if="languages.includes(serieTV.original_language)"
             :src="require(`../assets/img/${serieTV.original_language}.png`)"
            />
            <span v-else>{{ serieTV.original_language }}</span>
            <h4 class="pt-2" v-if="serieTV.overview === ''">Trama non disponibile</h4>
            <p v-else class="pt-2">{{ serieTV.overview }}</p>
            <i
              v-for="(vote, index) in getstars(serieTV.vote_average)"
              class="fa-solid fa-star ms_gold"
              :key="index"
            ></i>
            <i
               v-for="(star, i) in 5 - getstars(serieTV.vote_average)"
               class="fa-regular fa-star"
               :key="i"
            ></i>
        </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SeriesList",
  props: ["seriesTV"],

  data: function () {
    return {
      languages: ["en", "de", "es", "fr", "ja", "it"],
    };
  },
  methods: {
    getstars(number) {
      return Math.round(number / 2);
    },
  },
};
</script>

<style lang ="scss">

.ms_gold {
  color: gold;
}

.ms_color{
  color: whitesmoke;
}
</style>