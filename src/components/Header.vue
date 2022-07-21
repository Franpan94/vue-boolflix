<template>
  <header>
   <input type="text" v-model="textosearch" 
    @keyup.enter="$emit('search',textosearch)">
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