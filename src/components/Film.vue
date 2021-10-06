<template>
  <div>
    <li v-for="(item, index) in listFilms" :key="index">
      <h3>{{ listFilms[index].title }}</h3> 
      <h4>{{ listFilms[index].original_title }}</h4> 
      <div>{{ listFilms[index].original_language }}</div> 
      <div>{{ listFilms[index].vote_average }}</div> 
    </li>
  </div>
</template>

<script>

export default { 
  name: 'Film',

  props: ['listFilms'],

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>