<template>
  <section class="pt-4 row">
    <h1 class="pt-2 ms_color">Lista Film</h1>
    <div v-for="film in films" :key="film.id" class="col-3">
      <FilmCard :film = 'film'/>
    </div>
  </section>
</template>

<script>
import FilmCard from './FilmCard.vue'

export default {
  name: "FilmList",
  props: ["films"],

  components: {
    FilmCard
  }
};
</script>

<style lang ="scss">
.ms_color{
  color: whitesmoke;
}
</style>