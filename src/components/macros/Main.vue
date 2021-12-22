<template>
<main>
  <div class="container-100">
    <div class="container-80">
      <Search :filmsInput="films" />
    </div>
    <div class="container-80">
      <SearchTV :shows="shows" />
    </div>
     <div class="container-80">
      <MovieGenres :genres="genres" />
    </div>
  </div>
</main>
</template>

<script>
import Search from "../commons/Search.vue";
import SearchTV from "../commons/SearchTv.vue";
import MovieGenres from"../commons/MovieGenres.vue";
export default {
  name: "Main",
  components: {
    Search,
    SearchTV,
    MovieGenres,
    
  },
  props: {
    films: Array,
    shows: Array,
    genres:Array,
  },
  methods: {},
};
</script>

<style lang="scss" scoped></style>
