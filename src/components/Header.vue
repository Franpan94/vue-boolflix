<template>
  <header>
    <div class="text-center">
      <h1>Boolflix</h1>
    </div>
    <div class="container">
      <div class="d-flex justify-content-center">
        <div class="pt-3">
          <input 
            type="text"
            v-model.trim="textosearch"
            @keyup.enter="$emit('search', textosearch)"
          />
        </div>
        <div class="p-2">
          <button 
            type="button"
            class="btn btn-primary"
            @click="$emit('search', textosearch)"
          >
            Search
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",

  data: function () {
    return {
      textosearchfilms: "",
      textosearchseriesTV: "",
    };
  },
};
</script >

<style lang ="scss">

</style>