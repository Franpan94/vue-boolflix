<template>
  <section>
    <h1>{{film.title}}</h1>
    <h3>{{film.original_title}}</h3>
    <h3>{{film.original_language}}</h3>
    <h3>{{film.vote_average}}</h3>
  </section>
</template>

<script>
export default {
  name: 'FilmList',

  props: ['film']
}
</script>

<style>

</style>