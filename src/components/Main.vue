<template>
  <main class="d-flex justify-content-center">
    <FilmList class="ms_pl" :films = 'films'/>
    <SeriesList :seriesTV = 'seriesTV' />
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
    .ms_pl{
      padding-left: 250px;
    }
</style>