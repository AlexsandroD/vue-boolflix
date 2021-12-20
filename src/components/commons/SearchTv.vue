<template>
    <div class="search">
        <h3>serie tv</h3>
            <ul>
                <li v-for='(show, index) in tvShow' :key="index">{{show.title}},{{show.original_title}}</li>
            </ul>
    </div>
</template>

<script>
export default {
name:"SearchTV",
data(){
    return{
       TvShows:[],
    }
},
props:{
   shows:[]
},
methods:{
 
    
  
}
}
</script>

<style lang="scss" scoped>
  
</style>