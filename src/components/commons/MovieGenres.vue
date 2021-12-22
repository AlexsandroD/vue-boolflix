<template>
   <div class="search">
    <!-- <h3>Films</h3> -->
    <div class="container-80">
      <ul>
        <li  v-for="(g, index) in genres" :key="index">
          <h1>{{g.name}}</h1>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
 name: 'MovieGenres',
 props: {
     genres:Array
 }
}
</script>

<style lang="scss" scoped>

</style>