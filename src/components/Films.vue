<template>
    <div>
      <ul>
        <Film :listFilms="filmsFound"/>       
      </ul>
      <h1>-----------------------------------------------------------------------------------------</h1>
      <ul>
        <TVseries :listTVseries="TVseriesFound"/>       
      </ul>
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

  props: ['filmsFound', 'TVseriesFound'],

  name: 'Films',

  // methods: {
  //   function() {
  //     axios.get('https://api.themoviedb.org/3/search/movie', {
  //     params: {
  //       api_key: '754efc644ca164ed7ad0793e2816a304',
  //       query: 'Ritorno al futuro',
  //       language: 'it',
  //     }})

  //     .then( (response) => {
  //       console.log(response.data.results[0].adult);
  //       this.listFilms = response.data.results[0].adult;
  //     });
  //   }
  // },
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>