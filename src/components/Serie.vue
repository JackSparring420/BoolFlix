<template>
  <div class="serie">
      <div class="copertina">
        <img :src="imageSerie()" alt="">
      </div>    
    <div class="none">
      <span>Titolo</span> <h3>{{details.name}}</h3>
      <div class="separatore"></div>
      <span>Titolo originale:</span> <h4>{{details.original_name}}</h4>
      <div class="separatore"></div>
      <div>
          <span>Lingua originale:</span> <span class="language">{{details.original_language}} </span> <img :src="language()" class="flag"> 
      </div>
      <div class="separatore"></div>
      <span>Voto:</span> <span>{{voteStars()}}</span>
      <star-rating :rating="voteStars()" star-size="30" increment="0.25" :show-rating="false"></star-rating>
      <div class="separatore"></div>
      <span>Overview:</span> <p>{{details.overview}}</p>
    </div>
  </div> 
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
  name: "Movie",
   components: {
    StarRating
  },
  props: {
    details: Object,
  },
  data() {
    return {
      italia: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/1500px-Flag_of_Italy.svg.png",
      inghilterra: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Flag_of_the_United_Kingdom.svg/2560px-Flag_of_the_United_Kingdom.svg.png",
      mondo: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/Earth_Day_Flag.png/1280px-Earth_Day_Flag.png",
      img: "https://image.tmdb.org/t/p/w342",
      netflix: "https://travelnostop.com/wp-content/uploads/2019/11/netflix.png"
    };
  },
  methods: {
    language() {
      if (this.details.original_language == "it") {
        return this.italia;
      } else if (this.details.original_language == "en") {
        return this.inghilterra;
      } else {
        return this.mondo;
      }
    },

    imageSerie() {
      if (this.details.backdrop_path !== null) {
        console.log(this.details.backdrop_path);
        return this.img + this.details.backdrop_path;
      } else {
        return this.netflix;
      }
    },
    voteStars() {
      return (this.details.vote_average / 2)
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.serie {
 width: calc(100% / 6);
        height: 500px;
        border: 5px solid black;
        color: red;
        overflow: hidden;

            .copertina {
                width: 100%;
                height: 500px;
                img{
                    object-fit: cover;
                    // object-position: center;
                    width: 100%;
                    height: 100%;
                }
            } 
            h3, h4, p, .language {
                color: white;
                display: inline;
            }
            .separatore{
                height: 20px;
            }
            .flag {
                max-width: 10%;
                max-height: 10%;
            }
            .none {
                display: none;
            }
            

    }

    .serie:hover .none{
        display: block;
    }
    .serie:hover .copertina{
        display: none;
    }

</style>