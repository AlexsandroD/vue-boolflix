<template>
<main>
  <div class="container-100">
    <div class="container-80">
      <Search/>
    </div>
    <div class="container-80">
      <SearchTV/>
    </div>
     <div class="container-80">
    
    </div>
  </div>
</main>
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
};
</script>

<style lang="scss" scoped></style>
