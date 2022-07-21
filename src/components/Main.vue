<template>
  <main>
    <FilmList :film= 'film'/>
  </main>
</template>

<script>
import FilmList from "./FilmList.vue";

export default {
  name: "Main",
  components: {
    FilmList,
  },

  props: ['film']
};
</script>

<style lang="scss">

</style>