<template>
   <div class="search">
    <!-- <h3>Films</h3> -->
    <div class="container-80">
      <label>
        <select v-model="selectGenre">
          <option value="">Genres</option>
          <option class="selected"  v-for="(g, index) in dataShared.genres" :key="index">
            <h1>{{g.name}}</h1>
          </option>
        </select>
      </label>
    </div>
  </div>
</template>

<script>
import axios from'axios';
import dataShared from "../../share/dataShared";
export default {
 name: 'MovieGenres',
  data(){
    return{
      selectGenre:"",
      dataShared,
    }
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
      this.dataShared.genres = response.data.genres
      console.log(this.dataShared.genres)
    })
    .catch(function(error){
      console.log(error)
    })
  }
}
</script>

<style lang="scss" scoped>
.gg{
  color: white;
}


  select {
    padding:3px;
    margin: 0;
    -webkit-border-radius:4px;
    -moz-border-radius:4px;
    background: #181818;
    color:#fff;
    border:none;
    outline:none;
    display: inline-block;
    -webkit-appearance:none;
    -moz-appearance:none;
    appearance:none;
    cursor:pointer;
    option:hover{
      background-color: #181818;
    }
  
  }



/* Targetting Webkit browsers only. FF will show the dropdown arrow with so much padding. */
@media screen and (-webkit-min-device-pixel-ratio:0) {
    select {padding-right:18px}
}

label {position:relative}
label:after {
    content:'>';
    font:15px "Consolas", monospace;
    color:#fff;
    -webkit-transform:rotate(90deg);
    -moz-transform:rotate(90deg);
    -ms-transform:rotate(90deg);
    transform:rotate(90deg);
    right:8px; top:2px;
    padding:0 0 2px;
    position:absolute;
    pointer-events:none;
}
label:before {
    content:'';
    right:6px; top:0px;
    width:20px; height:20px;
    background:#181818;
    position:absolute;
    pointer-events:none;
}
</style>