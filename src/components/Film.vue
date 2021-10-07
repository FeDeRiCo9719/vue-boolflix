<template>
  <div>
    <h2 v-if="listFilms.length > 0" >Movies</h2>
    <ul>
      <li v-for="(item, index) in listFilms" :key="index">
        <h3>{{ listFilms[index].title }}</h3> 
        <h4>{{ listFilms[index].original_title }}</h4> 

        <!-- language -->
        <div class="language">
          <img v-if="flags.includes(listFilms[index].original_language)" :src="require(`../assets/img/flags/${listFilms[index].original_language}.png`)" alt="language icon">
          <div class="unknown" v-else alt="language unknown">?</div>          
        </div>

        <!-- stars votes -->
        <div>        
          <i  class="fas fa-star" v-for="(n,I) in movieStars" :key="I" :class="I < Math.round(listFilms[index].vote_average/2) ? 'yellow' : 'grey'" ></i>                   
        </div>
                        
        <!-- poster -->
        <img :src="('https://image.tmdb.org/t/p/w342' + listFilms[index].poster_path)" alt=""> <!-- https://image.tmdb.org/t/p/w342 -->
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

div {

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

  .yellow {
    color: rgb(221, 206, 0);
  }

  .grey {
    color: grey;
  }
}
</style>