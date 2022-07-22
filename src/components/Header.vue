<template>
  <header>
    <div class="text-center">
      <h1>Boolflix</h1>
    </div>
    <div class="container">
      <div class="d-flex justify-content-between">
        <div>
          <h1>Lista film</h1>
          <input
            type="text"
            v-model.trim="textosearchfilms"
            @keyup.enter="$emit('search', textosearchfilms)"
          />
          <div class="p-2">
            <button
              type="button"
              class="btn btn-primary"
              @click="$emit('search', textosearchfilms)"
            >
              Search
            </button>
          </div>
        </div>
        <div >
          <h1>Lista Serie TV</h1>
          <input
            type="text"
            v-model.trim="textosearchseriesTV"
            @keyup.enter="$emit('research', textosearchseriesTV)"
          />
          <div class="p-2">
            <button
              type="button"
              class="btn btn-primary"
              @click="$emit('research', textosearchseriesTV)"
            >
              Search
            </button>
          </div>
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
</script>

<style>
</style>