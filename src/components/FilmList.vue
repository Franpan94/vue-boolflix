<template>
  <section>
    <h3 v-for="film in films" :key="film.id">
      {{film.title}} - {{film.original_title}} - {{film.original_language}} - {{film.vote_average}}
    </h3>
    <img src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/160/google/80/flag-for-italy_1f1ee-1f1f9.png" alt="">
  </section>
</template>

<script>
export default {
  name: 'FilmList',

  props: ['films']
}
</script>

<style>

</style>