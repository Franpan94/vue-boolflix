<template>
  <header>
    <div class="text-center">
      <h1>Lista film</h1>
    </div>
   <input type="text" v-model.trim="textosearch" 
    @keyup.enter="$emit('search',textosearch)">
    <div class="p-2">
        <button type="button" class="btn btn-primary" @click="$emit('search',textosearch)" >Search</button>
    </div>

  </header>
</template>

<script>
export default {
   name: 'Header',

   data: function (){
      return{
        textosearch:""
      }
   }
}
</script>

<style>


</style>