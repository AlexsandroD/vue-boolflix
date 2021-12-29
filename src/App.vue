<template>
  <div id="app">
    <Header :genres="genres"/>
    <Main :genres="genres" />
  </div>
</template>

<script>
import axios from'axios';
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
      genres: [],
    };
  },

  

  methods: {
   
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
