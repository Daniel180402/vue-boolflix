<template>
  <div id="app">
    <Header @newSearch="updateMovieSearch"/>
    <Main :movies="movies"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import axios from "axios";

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data: function(){
    return {
      movieSearch: "",
      movies: [],
      apiURL : "https://api.themoviedb.org/3/search/movie?api_key=e99307154c6dfb0b4750f6603256716d&query=",
    }
  },
  methods: {
    updateMovieSearch(inputString){
      this.movieSearch = inputString;
      this.getMovies();
    },
    getMovies(){
      axios
      .get(this.apiURL + this.movieSearch)
      .then((response) => {
        console.log(response.data.results);
        this.movies = response.data.results;
      })
      .catch((error) => {
        console.log(error);
      });
    }
  }
}
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
@import "@/style/main-style.scss";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
