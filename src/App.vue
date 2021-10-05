<template>
  <div id="app">
    
    <Header @searchFilm="saveTextFilm" />
    <Films/>

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
  methods: {
    saveTextFilm(text) {
      console.log(text);
    }
  }
}
</script>

<style lang="scss">
@import './assets/style/common.scss';
</style>
