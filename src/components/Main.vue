<template>
  <main class="ms_bg_grey">
    <div v-if="((films.length > 0) && (seriesTV.length > 0))">
      <FilmList class="ms_pl_10" :films = 'films'/>
      <SeriesList :seriesTV = 'seriesTV' />
    </div>
    <div v-else>
      <h2>Nessun risultato trovato</h2>
    </div>
  </main>
</template>

<script>
import FilmList from "./FilmList.vue";
import SeriesList from "./SeriesList.vue";

export default {
  name: "Main",
  components: {
    FilmList,
    SeriesList
  },

  props: ['films', 'seriesTV']
};
</script>

<style lang="scss">
    .ms_bg_grey{
      background-color: grey;
      height: 100%;
    }

    .ms_pl_10{
      padding-left: 30px;
    }
</style>