<template>
    <div>
      <Film/>
      <button @click="print" >ciao</button>
    </div>
</template>

<script>
import Film from './Film.vue';
import axios from 'axios';

export default {
    
  name: 'Films',

  data() {
    return {
      listFilms: {},
    }
  },
  methods: {
    print() {
      console.log(this.listFilms);
    }
  },

  props: {
    
  },

  components: {
    Film
  },

  created() {
      axios.get('https://api.themoviedb.org/3/search/movie', {
      params: {
        api_key: '754efc644ca164ed7ad0793e2816a304',
        query: 'Ritorno al futuro',
        language: 'it',
      }
    })

    .then( (response) => {
      console.log(response.data.results[0]);
      console.log(this);
      this.listFilms = response.data.results;
    });
  }
  // axios.get("url").then
    
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>