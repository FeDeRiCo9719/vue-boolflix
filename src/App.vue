<template>
  <div id="app">
    
    <Header @searchFilm="saveTextFilm" />
    <Films :filmsFound="filmsFound" :TVseriesFound="TVseriesFound" />  <!-- :TVseriesFound="TVseriesFound" (props Tv series) -->
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue';
import axios from 'axios';

export default {
  name: 'App',

  components: {
    Header,
    Films
  },

  data() {
    return {
      filmsFound: [],
      TVseriesFound: []
    }
  },

  methods: {

    // saveTextFilm(text) {
    //   console.log(text);
    //   this.savedTextFilm = text;
    // },

    saveTextFilm(text) {
      // SEARCH MOVIES
      axios.get('https://api.themoviedb.org/3/search/movie', {
      params: {
        api_key: '754efc644ca164ed7ad0793e2816a304',
        query: text,
        language: 'it-IT',
      }})

      .then( (response) => {
        this.filmsFound = response.data.results;
        console.log(this.filmsFound[0]);
      });

      // SEARCH TV SERIES
      axios.get('https://api.themoviedb.org/3/search/tv', {
      params: {
        api_key: '754efc644ca164ed7ad0793e2816a304',
        query: text,
        language: 'it-IT',
      }})

      .then( (response) => {
        console.log(response.data.results);
        this.TVseriesFound = response.data.results;
        console.log(this.TVseriesFound[0]);
      });
    }
  },

}
</script>

<style lang="scss">
@import './assets/style/common.scss';
</style>
