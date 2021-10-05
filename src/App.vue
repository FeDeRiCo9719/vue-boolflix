<template>
  <div id="app">
    
    <Header @searchFilm="saveTextFilm" />
    <Films :savedTextFilm="savedTextFilm" />

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Films from './components/Films.vue';

export default {
  name: 'App',

  components: {
    Header,
    Films
  },

  data() {
    return {
      savedTextFilm:'',
    }
  },

  methods: {
    saveTextFilm(text) {
      console.log(text);
      this.savedTextFilm = text;
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
</style>
