<template>
  <header class="ms_bg">
    <div class="container">
      <div class="row">
        <div class="col-9">
          <h1 class="display-3 color-red">Boolflix</h1>

        </div>
        <div class="col-3 pt-4">
          <input placeholder="Cerca film o serie TV"
            class="pt-1 pb-2"
            type="text"
            v-model.trim="textosearch"
            @keyup.enter="$emit('search', textosearch)"
          />
          <button  
            type="button"
            class="btn btn-danger"
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
.color-red{
  color: red;
}

.ms_bg{
  background-color: black;
}

</style>