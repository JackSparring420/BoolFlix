<template>
  <div class="movie">
      <div>
        <img :src="img + details.backdrop_path" alt="">
      </div>
      <h3>{{details.title}}</h3>
      <div class="separatore"></div>
      <h3>{{details.original_title}}</h3>
      <div class="separatore"></div>
      <div>
          <!-- {{details.original_language}}  -->
          <img :src="linguage()"> 
        </div>
      <div class="separatore"></div>
      <div>{{details.vote_average}}</div>
  </div>
</template>

<script>
export default {
  name: 'Movie',
  props: {
      details:Object
  },
  data() {
    return {
      italia: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/1500px-Flag_of_Italy.svg.png",
      inghilterra: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Flag_of_the_United_Kingdom.svg/2560px-Flag_of_the_United_Kingdom.svg.png",
      img: "https://image.tmdb.org/t/p/w342",
    };
  },
  methods: {
      linguage() {
          if(this.details.original_language == "it") {
              return this.italia
          } else if (this.details.original_language == "en"){
              return this.inghilterra
          }
      },

      imageMovie() {
          this.img = "https://image.tmdb.org/t/p/w342" + this.details.backdrop_path
      }
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
                max-width: 30%;
                max-height: 0%;
            }
    }

</style>