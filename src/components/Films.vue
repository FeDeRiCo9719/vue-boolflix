<template>
    <div>
      <!-- Movies -->
      <Film :listFilms="filmsFound"/>            
      <div>-----------------------------------------------------------------------------------------</div>
      <!-- TV series -->
      <TVseries :listTVseries="TVseriesFound"/>            
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
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>