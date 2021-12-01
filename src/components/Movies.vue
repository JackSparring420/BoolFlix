<template>
  <main>
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
  width: 60%;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  padding: 50px;

  .movie {
    flex-wrap: wrap;
    justify-content: space-between;
    margin-top: 20px;
  }
}
  #filtro{
    display: flex;
    justify-content: center;
    padding-top: 50px ;
  }
</style>
