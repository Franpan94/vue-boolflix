<template>
  <section>
      <h3 v-for="serieTV in seriesTV" :key="serieTV.id">
          {{serieTV.title}} - {{serieTV.original_title}} - {{serieTV.original_language}} - {{serieTV.vote_average}}
      </h3>
  </section>
</template>

<script>
export default {
 name: 'SeriesList',
 props: ['seriesTV']
}
</script>

<style>

</style>