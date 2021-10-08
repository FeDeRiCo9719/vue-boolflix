<template>
    <div class="container">
      <!-- impaginazione home esempio -->
      <div class="hero" v-if="savedText == ''">
        <div class="text-hero">
          <h1>Film, serie TV e tanto altro. Senza limiti.</h1>
          <p>Guarda ciò che vuoi ovunque. Disdici quando vuoi.</p>
        </div>       
      </div>
    
      <main>
        <!-- Movies -->
        <Film :listFilms="filmsFound"/>
        <hr v-if="TVseriesFound.length > 0">
        <!-- TV series -->
        <TVseries :listTVseries="TVseriesFound"/>

        <!-- No results -->
        <h2 v-if="savedText != '' & filmsFound.length <1 & TVseriesFound.length <1 " >Sorry, no results for "{{ savedText }}"</h2>
      </main>
             
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
.container {
  .hero {
    background-image: url('../assets/img/hero.jpg');
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    height: 100vh;
    color: white;
    text-align: center;

    .text-hero {
      width: 60%;
      font-size: 20px;
      color: rgb(212, 212, 212);
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 2;

      h1 {
        margin-bottom: 20px;
        font-size: 40px;
        color: white;
      }
    }
  }
}
main {
  padding-top: 100px;
  color: white;
}
</style>