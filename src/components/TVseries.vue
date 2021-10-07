<template>
  <div>
    <h2 v-if="listTVseries.length > 0" >TV Series</h2>
    <h2 v-if="listTVseries.length < 0" >TV Series</h2>
    <ul>
      <li v-for="(item, index) in listTVseries" :key="index">
        <h3>{{ listTVseries[index].name }}</h3> 
        <h4>{{ listTVseries[index].original_name }}</h4> 
        <div>{{ listTVseries[index].original_language }}</div> 
        <div>{{ listTVseries[index].vote_average }}</div>
        <img :src="('https://image.tmdb.org/t/p/w342' + listTVseries[index].poster_path)" alt=""> <!-- https://image.tmdb.org/t/p/w342 --> 
      </li>
    </ul>
  </div>
</template>

<script>

export default { 
  name: 'TVseries',

  props: ['listTVseries'],

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>