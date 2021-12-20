<template>
    <div class="search">
            <input type="text" v-model='inputSearch'>
            <button @click="getApi()">Click me</button>
            <ul>
                <li v-for='(film, index) in films' :key="index">{{film.title}},{{film.original_title}},{{film.original_language}}</li>
            </ul>
    </div>
</template>

<script>
import axios from 'axios';
export default {
name:"Search",
data(){
    return{
        films:[],
        inputSearch:"",
    }
},
methods:{
   getApi () {
        axios.get('https://api.themoviedb.org/3/search/movie', {
            params: {
                api_key:'86b1172b207765fe60ddcff01203c51b',
                query:this.inputSearch,
                language:'it-IT'
            }
        })
        .then((response) => {
            console.log(response)
            this.films=(response.data.results)
        })
        .catch(function (error) {
             console.log(error);
        })
   }
}
}
</script>

<style lang="scss" scoped>

</style>