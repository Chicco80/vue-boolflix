<template>
  <div id="app">
    <header>
      <h1>Boolfix</h1>
      <app-search @performSearch= 'search'/>
    </header>
    <main>
      <app-grid :items="movies" title="Movies"/>
      <app-grid :items="series" title="Series"/>
    
    </main>

  </div>
</template>

<script>
import AppGrid from './components/AppGrid.vue'
import AppSearch from './components/AppSearch.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    AppSearch,
    AppGrid,
  },
  data(){
    return{
      apiImg: 'https://image.tmdb.org/t/p/w342',
      apiKey:'e99307154c6dfb0b4750f6603256716d',
      apiPath:'https://api.themoviedb.org/3/search/',
      movies:[],
      series:[],
      
      
    }
  },
  methods:{
    getMovies(queryParams){
      axios.get(this.apiPath + 'movie', queryParams).then((res)=>{
        this.movies = res.data.results;
                console.log(this.movies)

      }).catch((error)=>{
        console.log(error)
      });
    },
      getSeries(queryParams){
      axios.get(this.apiPath + 'tv', queryParams).then((res)=>{
        this.series = res.data.results;
                console.log(this.movies)

      }).catch((error)=>{
        console.log(error)
      });
    },
    search(text){
      console.log(text);
      const queryParams = {
        params:{
          api_key: this.apiKey,
          query: text,
          language:'it-IT',
        },
       
    }
    this.getMovies(queryParams);
    this.getSeries(queryParams);


  }
  }
}
</script>


<style lang="scss">
  @import './assets/style/general.scss';

  h1{
    color: red;
  }
  header{
    background-color: black;
    display: flex;
    justify-content: space-around;
  }

</style>
