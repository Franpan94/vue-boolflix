<template>
  <main class="ms_bg_grey">
    <div v-if="((films.length > 0) && (seriesTV.length > 0))">
      <FilmList class="ms_pl_30 ms_pr_30" :films = 'films'/>
      <SeriesList class="ms_pl_30 ms_pr_30" :seriesTV = 'seriesTV' />
    </div>
    <div v-else>
      <h2 class="ms_pl_30 ms_pr_30">Nessun risultato trovato</h2>
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
      height: 1000vh;
    }

    .ms_pl_30{
      padding-left: 30px;
    }

    .ms_pr_30{
      padding-right: 30px;
    }
</style>