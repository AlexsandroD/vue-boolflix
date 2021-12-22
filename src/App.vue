<template>
  <div id="app">
    <Header @search="searching" />
    <Main :films="films" :shows="shows" :genres="genres" />
  </div>
</template>

<script>
import axios from "axios";
import Main from "./components/macros/Main.vue";
import Header from "./components/macros/Header.vue";
export default {
  name: "App",
  components: {
    Main,
    Header,
  },
  data() {
    return {
      dataSearch: "",
      films: [],
      shows: [],
      genres: [],
    };
  },

  

  methods: {
    searching(payload) {
      this.dataSearch = payload;
      this.getMovieApi();
      this.getTvshow();
    },
    getMovieApi() {
      if (this.dataSearch != "") {
        axios
          .get("https://api.themoviedb.org/3/search/movie", {
            params: {
              api_key: "86b1172b207765fe60ddcff01203c51b",
              query: this.dataSearch.toUpperCase(),
              language: "it-IT",
            },
          })
          .then((response) => {
            console.log(response);
            this.films = response.data.results;
          })
          .catch(function (error) {
            console.log(error);
          });
      } else {
        alert("please write a title");
      }
    },

    getTvshow() {
      if (this.dataSearch != "") {
        axios
          .get("https://api.themoviedb.org/3/search/tv", {
            params: {
              api_key: "86b1172b207765fe60ddcff01203c51b",
              query: this.dataSearch,
              language: "it-IT",
            },
          })
          .then((response) => {
            console.log(response);
            this.shows = response.data.results;
          })
          .catch(function (error) {
            console.log(error);
          });
      } else {
        alert("please write a title");
      }
    },
  },

  created(){
    axios.get("https://api.themoviedb.org/3/genre/movie/list",{
      params:{
        api_key: "86b1172b207765fe60ddcff01203c51b",
        language: "it-IT",
      }
    })
    .then((response) => {
      console.log(response)
      this.genres = response.data.genres
      console.log(this.genres)
    })
    .catch(function(error){
      console.log(error)
    })
  }

};
</script>

<style lang="scss">
@import "./assets/global.scss";
#app {
}
</style>
