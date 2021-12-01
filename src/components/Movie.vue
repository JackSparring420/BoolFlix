<template>
  <div class="movie">
      <h3>{{details.title}}</h3>
      <div class="separatore"></div>
      <h3>{{details.original_title}}</h3>
      <div class="separatore"></div>
      <div>{{details.original_language}}</div>
      <div class="separatore"></div>
      <div>{{details.vote_count}}</div>
  </div>
</template>

<script>
export default {
  name: 'Movie',
  props: {
      details:Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .movie {
        text-align: center;
        width: calc(100% / 6);
        padding: 25px;
        background: rgba($color: #000000, $alpha: 0.3);
            h3 {
                color: white;
            }
            .separatore{
                height: 20px;
            }
            img {
                max-width: 100%;
                max-height: 100%;
            }
    }

</style>