<template>
  <main>
      <h3>
          serie
      </h3>
    <div id="series-container">
      <Serie v-for="serie, i in series" :key="i" :details="serie" />
    </div>
  </main>
</template>

<script>
import Serie from "@/components/Serie.vue";

export default {
  name: "Series",
  components: {
    Serie,
  },
  props: {
    series: Array
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
main {
  background-color: #1e2d3b;
}
#series-container {
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
