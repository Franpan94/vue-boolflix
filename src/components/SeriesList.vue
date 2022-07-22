<template>
  <section class="pt-2">
      <h6 v-for="serieTV in seriesTV" :key="serieTV.id">
            {{serieTV.name}} - {{serieTV.original_name}} - {{serieTV.vote_average}}
            <img v-if="serieTV.original_language==='it'" src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/160/google/80/flag-for-italy_1f1ee-1f1f9.png" alt="" class="ms_width">
            <img v-else-if="serieTV.original_language==='en'" src=https://www.bandiere-mondo.it/data/flags/emoji/facebook/256x256/gb.png alt="" class="ms_width">
            <img v-else-if="serieTV.original_language==='de'" src=https://www.bandiere-mondo.it/data/flags/emoji/facebook/256x256/de.png alt="" class="ms_width">
            <img v-else-if="serieTV.original_language==='es'" src=https://www.emojimeaning.com/img/img-apple-160/1f1ea-1f1f8.png alt="" class="ms_width">
            <img v-else-if="serieTV.original_language==='fr'" src=https://www.bandiere-mondo.it/data/flags/emoji/facebook/256x256/fr.png alt="" class="ms_width">
            <img v-else-if="serieTV.original_language==='ja'" src=https://emojis.wiki/emoji-pics/apple/japan-apple.png alt="" class="ms_width">
            <h6 v-else>{{film.original_language}}</h6>
        </h6>
    </section>
</template>

<script>
export default {
 name: 'SeriesList',
 props: ['seriesTV']
}
</script>

<style>

</style>