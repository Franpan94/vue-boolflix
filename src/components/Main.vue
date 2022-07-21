<template>
  <main>
    <FilmList :search= 'search'/>
  </main>
</template>

<script>
import FilmList from "./FilmList.vue";

export default {
  name: "Main",
  components: {
    FilmList,
  },

  props: ['search']
};
</script>

<style lang="scss">

</style>