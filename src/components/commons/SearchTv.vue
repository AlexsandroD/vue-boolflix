<template>
    <div class="search">
        <h3>serie tv</h3>
        <div class="container-80">
            <ul>
                <li v-for='(show, index) in shows' :key="index"><img :src="`http://image.tmdb.org/t/p/w300/${show.backdrop_path}`" alt="Immagine non disponibile">{{show.name}},{{show.original_title}},Voto:{{show.vote_average}} </li>
            </ul>
        </div>
    </div>
    <!-- <span><img :src="`https://flagcdn.com/16x12/${show.original_language}.png `"></span>  -->
</template>

<script>
export default {
name:"SearchTV",
props:{
   shows:[]
},

methods:{
 
    
  
}
}
</script>

<style lang="scss" scoped>
.container-80{
        ul{
            width: 70%;
            margin: 60px auto;
            display: grid;
            justify-content: center;
            grid-template-columns:repeat(auto-fill, 200px);
            column-gap:30px;
            row-gap: 20px;
            li{
                img{
                    width: 100%;
                }
            }
        }
    }

  
</style>