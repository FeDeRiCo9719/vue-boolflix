<template>
  <div>
    <li v-for="(item, index) in listTVseries" :key="index">
      <h3>{{ listTVseries[index].name }}</h3> 
      <h4>{{ listTVseries[index].original_name }}</h4> 
      <div>{{ listTVseries[index].original_language }}</div> 
      <div>{{ listTVseries[index].vote_average }}</div> 
    </li>
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