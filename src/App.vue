<template>
  <div id="app">
    <MyHeader @search="searching"/>
    <main>
      <Movies :movies="movies" />
    </main>
  </div>
</template>

<script>
import axios from 'axios';
import MyHeader from './components/MyHeader.vue'
import Movies from './components/Movies.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    Movies
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=9e464d54d22c36357a80172c75c77726&language=IT&query=",
      searchText: '',
      movies: []
    };
  },
  methods: {
    getMovies() {
      const url = this.apiUrl+this.searchText+"&page=1&include_adult=false";
      axios.get(url).then((result) => {
        this.movies = result.data.results;
        console.log(result.data.results);
      });
    },
    searching(movies) {
      this.searchText = movies;
      this.getMovies();
    },
  },
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  } 
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #807062;
}
</style>
