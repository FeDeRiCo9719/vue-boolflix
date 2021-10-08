<template>
  <div class="ContainerFilms">
    <h2 v-if="listFilms.length > 0" >Movies</h2>
    <hr v-if="listFilms.length > 0">
    <ul>
      <li v-for="(item, index) in listFilms" :key="index">

        <div class="trama">{{ listFilms[index].overview }}</div>

        <!-- poster -->
        <div class="poster">
          <img :src="('https://image.tmdb.org/t/p/w342' + listFilms[index].poster_path)" alt=""> <!-- https://image.tmdb.org/t/p/w342 -->
        </div>

        <div class="bottomBox">
          <!-- info -->
          <div class="info">
            <div class="title">{{ listFilms[index].title }}</div> 
            <div>{{ listFilms[index].overview }}</div>
          </div>
        
          <!-- language -->
          <div class="language">
            <img v-if="flags.includes(listFilms[index].original_language)" :src="require(`../assets/img/flags/${listFilms[index].original_language}.png`)" alt="language icon">
            <div class="unknown" v-else alt="language unknown">?</div>          
          </div>

          <!-- stars votes -->
          <div>        
            <i  class="fas fa-star" v-for="(n,I) in movieStars" :key="I" :class="I < Math.round(listFilms[index].vote_average/2) ? 'yellow' : 'grey'" ></i>                   
          </div>
        </div>    

      </li>
    </ul>
  </div>
</template>

<script>

export default { 
  name: 'Film',
  props: ['listFilms'],
  data() {
    return {
      flags: ['de','en','es','fr','it','ja','pt',],
      movieStars: [1,2,3,4,5]
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.ContainerFilms {
  width: 95%;
  margin: auto;

  h2 {
    font-size: 30px;
    text-align: center;
    margin: 10px 0;
  }
  hr {
    margin-bottom: 20px;
    border-color: rgba(255, 255, 255, 0.445);
  }
  ul {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  li {
    cursor: pointer;
    display: inline-block;
    margin: 10px;
    // padding: 10px;
    width: 250px;
    height: 350px;
    background-color: rgb(47, 55, 68);
    // border-radius: 10px;
    position: relative;

    &:hover .trama {
      display: flex;
      color: black;
    }

    .trama {
      position: absolute;
      background-color: rgba(255, 255, 255, 0.719);
      font-weight: 500;
      // border-radius: 10px;
      width: 100%;
      height: 100%;
      cursor: pointer;
      font-size: 15px;
      padding: 10px;
      white-space: wrap; 
      overflow: hidden;
      text-overflow: ellipsis; 
      display: none;
    }

    .info {
      div {
        width: 150px;
        font-size: 12px;
        white-space: nowrap; 
        overflow: hidden;
        text-overflow: ellipsis; 
        margin: 5px 0;
        color: rgb(158, 158, 158);
      }
      .title {
        font-size: 15px;
        font-weight: 500;
        color: rgb(255, 255, 255);
      }

    }
    .bottomBox {
      padding: 10px;
      // display: flex;
      // justify-content: space-between;
      margin-top: 20px;
    }
  }

  // language
  .language {
    width: 20px;

    img {
      width: 100%;
    }

    .unknown {
      width: 100%;
      height: 20px;
      text-align: center;
      line-height: 20px;
      background-color: rgb(126, 126, 126);
      color: rgb(255, 255, 255);
      border-radius: 50%;
    }
  }
  // stars colors
  .yellow {
    color: rgb(221, 206, 0);
  }
  .grey {
    color: grey;
  }
  // posters
  .poster {
    width: 100%;
    height: 220px;
    background-color: grey;
    overflow: hidden;

    img {
      width: 100%;
    }
  }
}
</style>