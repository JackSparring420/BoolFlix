<template>
  <div id="no-search" v-if="movies.length === 0">Nessun risultato trovato</div>
  <main v-else>
    <h2>Movies</h2>
    <div id="movies-container">
      <Movie v-for="movie, i in movies" :key="i" :details="movie" />
    </div>
  </main>
</template>

<script>
import Movie from "@/components/Movie.vue";

export default {
  name: "Movies",
  components: {
    Movie,
  },
  props: {
    movies: Array
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#no-search {
  text-align: center;
  padding: 25px;
  font-size: 25px;
}

main {
  background-color: #1e2d3b;

  #movies-container {
    margin: auto;
    display: flex;
    flex-wrap: wrap;
    padding: 50px;

  }

  h2 {
    user-select: none;
  }
}
  
</style>
