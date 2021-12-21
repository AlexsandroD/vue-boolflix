<template>
  <div class="search">
    <h3>Films</h3>
    <div class="container-70">
      <ul>
        <li v-for="(film, index) in filmsInput" :key="index">
          <img
            :src="`http://image.tmdb.org/t/p/w200/${film.backdrop_path}`"
            alt="Poster Image"
          />{{ film.title }},{{ film.original_title }},Voto:{{
            film.vote_average
          }}
          <span
            ><img
              :src="`https://flagcdn.com/16x12/${getFlag(
                film.original_language
              )}.png`"
          /></span>
        </li>
      </ul>
    </div>
  </div>
  <!-- <span><img :src="`https://flagcdn.com/1x1/${film.original_language}.png `"></span>  -->
</template>

<script>
export default {
  name: "Search",
  props: {
    filmsInput: Array,
  },
  data() {
    return {
      voteFilm: 0,
    };
  },
  methods: {
    getFlag(lang) {
      if (lang == "en") {
        return "gb";
      }
      return lang;
    },
  },
};
</script>

<style lang="scss" scoped>
.container-70 {
  width: 70%;
  margin: 50px auto;
  ul {
    display: grid;
    justify-content: center;
    grid-template-columns: repeat(auto-fill, 200px);
    column-gap: 30px;
    row-gap: 20px;
    li {
      img[src] {
        text-transform: uppercase;
      }
      img {
        width: 100%;
      }
      span {
        img {
          width: 16px;
          height: 12px;
        }
      }
    }
  }
}
</style>
