<template>
    <div class="search">
            <ul>
                <li v-for='(film, index) in films' :key="index">{{film.title}},{{film.original_title}}</li>
            </ul>
    </div>
</template>

<script>
export default {
name:"Search",
data(){
    return{
        
    }
},

props:{
    filmsInput:Array
}

}
</script>

<style lang="scss" scoped>
    img[src]{
        text-transform: uppercase;
    }
</style>