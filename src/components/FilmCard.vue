<template>
  <section class="ms_hover">
    <h2>{{ film.title }}</h2>
    <img
      :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`"
      :alt="film.title"
      class="ms_width_img pt-2 pb-4"
    />
    <div class="ms_bg_black p-2 ms_none">
      <h3>{{ film.original_title }}</h3>
      <img
        v-if="languages.includes(film.original_language)"
        :src="require(`../assets/img/${film.original_language}.png`)"
        class="ms_width"
      />
      <span v-else>{{ film.original_language }}</span>
      <h4 class="pt-2" v-if="film.overview === ''">Trama non disponibile</h4>
      <p v-else class="pt-2">{{ film.overview }}</p>
      <i
        v-for="(vote, index) in getstars(film.vote_average)"
        class="fa-solid fa-star ms_gold"
        :key="index"
      ></i>
      <i
        v-for="(star, i) in 5 - getstars(film.vote_average)"
        class="fa-regular fa-star"
        :key="i"
      ></i>
    </div>
  </section>
</template>

<script>
export default {
  name: "FilmCard",

  props: ["film"],

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

<style lang='scss'>
.ms_width {
  width: 50px;
  padding-left: 5px;
}

.ms_hover:hover .ms_width_img {
   display: none;
}

.ms_hover:hover .ms_bg_black {
   display: block;
}

.ms_bg_black {
  background-color: black;
  color: white;
  border: 2px solid white;
}

.ms_none {
  display: none;
}

h2{
  
  padding-top: 20px;
}

</style>