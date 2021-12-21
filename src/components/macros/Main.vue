<template>
  <div class="container-100">
    <div class="container-80">
      <Search :filmsInput="films" />
    </div>
    <div class="container-80">
      <SearchTV :shows="shows" />
    </div>
  </div>
</template>

<script>
import Search from "../commons/Search.vue";
import SearchTV from "../commons/SearchTv.vue";
export default {
  name: "Main",
  components: {
    Search,
    SearchTV,
  },
  props: {
    films: Array,
    shows: Array,
  },
  methods: {},
};
</script>

<style lang="scss" scoped></style>
