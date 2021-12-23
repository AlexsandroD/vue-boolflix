<template>
   <div class="search">
    <!-- <h3>Films</h3> -->
    <div class="container-80">
      <select v-model="selectGenre" @change="$emit('selection',selectGenre)">
        <option  v-for="(g, index) in genres" :key="index">
          <h1>{{g.name}}</h1>
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
 name: 'MovieGenres',
  data(){
    return{
      selectGenre:""
    }
  },
 props: {
     genres:Array
 }
}
</script>

<style lang="scss" scoped>

</style>