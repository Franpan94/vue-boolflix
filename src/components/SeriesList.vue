<template>
  <section class="pt-4 row">
    <h1 class="pt-2 ms_color">Lista SerieTV</h1>
    <div v-for="serieTV in seriesTV" :key="serieTV.id" class="col-3">
      <SeriesCard  :serieTV = 'serieTV'/>
    </div>
  </section>
</template>

<script>
import SeriesCard from './SeriesCard.vue'

export default {
  name: "SeriesList",
  props: ["seriesTV"],

  components: {
    SeriesCard
  }
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