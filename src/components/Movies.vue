<template>
  <main>
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
main {
  background-color: #1e2d3b;
}
#movies-container {
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  padding: 50px;
}
  
</style>
