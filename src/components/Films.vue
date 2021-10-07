<template>
    <div>
      <!-- impaginazione home esempio -->
      <div>
        <h1>BOOLFLIX</h1>
        <h3>Watch your Movies</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Illum laborum aliquid dolore pariatur laboriosam nihil. Repellendus dolorem animi nulla adipisci fuga, eligendi doloribus provident, cumque quae natus amet quisquam similique!</p>
      </div>
      <hr>

      <!-- Movies -->
      <Film :listFilms="filmsFound"/>
      <hr v-if="TVseriesFound.length > 0">
      <!-- TV series -->
      <TVseries :listTVseries="TVseriesFound"/>

      <!-- No results -->
      <h2 v-if="filmsFound.length === 0 & TVseriesFound.length === 0 & savedText != '' " >Sorry, no results for "{{ savedText }}"</h2>
             
    </div>
</template>

<script>
import Film from './Film.vue';
import TVseries from './TVseries.vue';
// import axios from 'axios';

export default {
  components: {
    Film,
    TVseries
  },
  props: ['filmsFound', 'TVseriesFound', 'savedText'],
  name: 'Films',   
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>