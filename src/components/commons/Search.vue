<template>
    <div class="search">
            <h3>Films</h3>
            <div class="">
                <ul>
                    <li v-for='(film, index) in filmsInput' :key="index"><img :src="`http://image.tmdb.org/t/p/w200/${film.backdrop_path}`" alt="Poster Image">{{film.title}},{{film.original_title}},Voto:{{film.vote_average}} </li>
                </ul>
            </div>
    </div>
    <!-- <span><img :src="`https://flagcdn.com/1x1/${film.original_language}.png `"></span>  -->
</template>

<script>
export default {
name:"Search",
props:{
    filmsInput:Array
},
data(){
    return{
        voteFilm:0
    }
},

}
</script>

<style lang="scss" scoped>
    .container-80{
            ul{
                width: 80%;
                margin: 60px auto;
                display: grid;
                justify-content: center;
                grid-template-columns:repeat(auto-fill, 200px);
                column-gap:30px;
                row-gap: 20px;
                li{
                    img[src]{
                        text-transform: uppercase;
                    }
                    img{
                        width: 100%;
                    }
            }
            }
        }
    
</style>