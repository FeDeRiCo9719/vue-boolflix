<template>
  <div>
    <h2 v-if="listTVseries.length > 0" >TV Series</h2>
    <ul>
      <li v-for="(item, index) in listTVseries" :key="index">
        <h3>{{ listTVseries[index].name }}</h3> 
        <h4>{{ listTVseries[index].original_name }}</h4>

        <!-- language -->
        <div class="tvLanguage">
          <img v-if="flagsTV.includes(listTVseries[index].original_language)" :src="require(`../assets/img/flags/${listTVseries[index].original_language}.png`)" alt="language icon TV">
          <div class="TVunknown" v-else alt="language unknown TV">?</div>          
        </div> 

        <!-- stars votes -->
        <div>
          <i class="fas fa-star" v-for="(n,I) in starsTV" :key="I" :class="I < Math.round(listTVseries[index].vote_average/2) ? 'yellow' : 'grey'"></i>
        </div> 
      
        <img :src="('https://image.tmdb.org/t/p/w342' + listTVseries[index].poster_path)" alt=""> <!-- https://image.tmdb.org/t/p/w342 --> 
      </li>
    </ul>
  </div>
</template>

<script>

export default { 
  name: 'TVseries',

  props: ['listTVseries'],
  data() {
    return {
      flagsTV: ['de','en','es','fr','it','ja','pt',],
      starsTV: [1,2,3,4,5]
    }
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.tvLanguage {
  width: 20px;
  img {
    width: 100%;
  }
  .TVunknown {
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
</style>