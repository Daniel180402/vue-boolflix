<template>
  <div id="app">
    <Header @searchFilm="search"/>
    <Main />
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
      searchString: "",
      filmList: [],
    }
  },
  created(){
    this.getApiList(); 
  },
  methods: {
    search(stringSearch){
      console.log(stringSearch);
      this.searchString = stringSearch;
    },
    getApiList(){
      axios.get("https://api.themoviedb.org/3/search/movie?api_key=c9b1c8be0be8a6b74147cc760fbd0280&query=star")
      .then((result) => {
        this.filmList = result.data.response;
        console.table(this.filmList);
      })
      .catch((error) => {
        console.error(error);
      })
    },
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
