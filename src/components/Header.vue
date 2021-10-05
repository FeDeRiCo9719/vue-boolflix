<template>
  <header>
    <form>
      <input type="text" placeholder="Search.." v-model="textFilmSearch" >
      <button @click.prevent="$emit('searchFilm', textFilmSearch )" >Search</button>
    </form>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      textFilmSearch: '',
    }
  },
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  background-color: rgb(75, 75, 75);
  padding: 20px;
}
</style>
