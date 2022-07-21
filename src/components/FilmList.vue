<template>
  <section>
    <h1>{{search.title}}</h1>
    <h2>{{search.original_title}}</h2>
    <h2>{{search.original_language}}</h2>
    <h2>{{search.vote_average}}</h2>
  </section>
</template>

<script>
export default {
  name: 'FilmList',

  props: ['search']
}
</script>

<style>

</style>