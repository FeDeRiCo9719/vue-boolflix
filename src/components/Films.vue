<template>
    <div>
      <Film/>
      <!-- <button @click="call" >call</button> -->
      <!-- <h2>{{ listFilms }}</h2> -->
    </div>
</template>

<script>
import Film from './Film.vue';
// import axios from 'axios';

export default {
  props: ['savedTextFilm'],

  name: 'Films',

  data() {
    return {
      // listFilms: [],
    }
  },

  // methods: {
  //   call() {
  //     axios.get('https://api.themoviedb.org/3/search/movie', {
  //     params: {
  //       api_key: '754efc644ca164ed7ad0793e2816a304',
  //       query: 'Ritorno al futuro',
  //       language: 'it',
  //     }
  //   })

  //   .then( (response) => {
  //     console.log(response.data.results[0].adult);
  //     this.listFilms = response.data.results[0].adult;
  //   });
  //   }
  // },
  components: {
    Film
  },
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>