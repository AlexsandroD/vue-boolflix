<template>
    <div class="container-100">
        <input type="text" v-model='inputSearch'>
        <button @click="getMovieApi();getTvshow()">Click me</button>
        <div class="container-80">
            <Search :filmsInput='films'/>
        </div>
        <div class="container-80">
            <SearchTV :shows='shows'/>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Search from"../commons/Search.vue";
import SearchTV from"../commons/SearchTv.vue";
export default {
    name:'Main',
    components:{
        Search,
        SearchTV,
    },
    data(){
        return{
            films:[],
            shows:[],
            inputSearch:"", 
        }
    },
    methods:{
    getMovieApi () {
        if(this.inputSearch != ''){
            
            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key:'86b1172b207765fe60ddcff01203c51b',
                    query:this.inputSearch.toUpperCase(),
                    language:'it-IT',
                }
            })
            .then((response) => {
                console.log(response)
                this.films = response.data.results
            })
            .catch(function (error) {
                    console.log(error);
            })
        }else{
            alert('please write a title')
        }
    },

    getTvshow(){
        if(this.inputSearch != ''){
            
            axios.get('https://api.themoviedb.org/3/search/tv', {
                params: {
                    api_key:'86b1172b207765fe60ddcff01203c51b',
                    query:this.inputSearch,
                    language:'it-IT',
                }
            })
            .then((response) => {
                console.log(response)
                this.shows= response.data.results 
                console.log(this.flag)
            })
            .catch(function (error) {
                    console.log(error);
            })
        }else{
            alert('please write a title')
        }
    },
    }

}
</script>

<style lang="scss" scoped>
    
</style>