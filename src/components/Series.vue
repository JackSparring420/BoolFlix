<template>
  <div v-if="series.length === 0"></div>
  <main v-else>
    <h2>Serie TV</h2>
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
  
  #series-container {
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
