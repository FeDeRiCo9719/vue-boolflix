<template>
  <header>
    <div class="logo">
      <h2>BOOLFLIX</h2>
    </div>
    <form>
      <button @click.prevent="$emit('searchFilm', textFilmSearch )" ><i class="fas fa-search"></i></button>
      <input type="text" placeholder="Search.." v-model="textFilmSearch" >
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

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  width: 100%;
  z-index: 10;
  position: fixed;

  display: flex;
  justify-content: space-between;
  align-items: center;

  height: 80px;
  padding: 0px 20px;
  background-color: rgb(47, 55, 68);
  // border-bottom: 1px solid rgba(255, 255, 255, 0.582);
  padding: 20px;

  .logo {
    font-size: 24px;
    color:rgb(45, 203, 243);
    cursor: pointer;
  }

  input {
    padding-left: 10px;
    height: 40px;
    outline: none;
    background-color: rgb(190, 206, 216);
    border: 1px solid rgba(128, 128, 128, 0);
    border-radius: 0px 20px 20px 0px;
    color: rgb(68, 68, 68);
  }
  button {
    // padding: 10px;
    height: 40px;
    width: 40px;
    cursor: pointer;
    border: 1px solid rgba(128, 128, 128, 0);
    background-color: rgb(190, 206, 216);
    color: rgb(39, 39, 39);
    border-radius: 20px 0px 0px 20px;
    &:hover {
      color: rgb(83, 98, 129);
    }

    i {
      font-size: 14px;
      text-align: center;
    }
  }
}
</style>
