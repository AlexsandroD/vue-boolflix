<template>
    <div class="search">
        <!-- <h3>serie tv</h3> -->
        <div class="container-70">
            <ul>
                <li v-for='(show, index) in shows' :key="index"><img :src="`${getImg(show.poster_path)}`" alt="Immagine non disponibile">
                <div class="text">
                    <h4>Titolo:{{show.name}}</h4>
                    <p v-if="show.title != show.original_title" >Titolo originale:{{show.original_title}}</p>
                    <p v-else></p>
                    <p>Trama:{{show.overview}}</p>
                    <div>Voto:<span>{{star(show.vote_average)}}</span></div>
                    <span><img :src="`https://flagcdn.com/16x12/${getFlag(show.original_language)}.png`"></span> 
                </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
name:"SearchTV",
data(){
    return{
        //  source:'http://image.tmdb.org/t/p/w300/'
    }
},
props:{
   shows:[],
},
  methods: {
       star(number){
        number = number / 2
        number = Math.ceil(number)
        switch(number) {
        case 0:
            number == 0
            number = '☆☆☆☆☆'
        break;
        case 1:
             number == 1
             number = '★☆☆☆☆'
        break;
        case 2:
             number == 2
             number = '★★☆☆☆'
        break;
        case 3:
             number == 3
             number = '★★★☆☆'
        break;
        case 4:
             number == 4
             number = '★★★★☆'
        break;
        case 5:
             number == 5
             number = '★★★★★'
        break;
}
        return number
    },
  
    getImg(lang){
        if(lang == null){
          lang = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT1j5dT8vlJwX_nr02NYSRfsr_pH4fyaxIqFw&usqp=CAU';
        }else{
            lang = 'http://image.tmdb.org/t/p/w1280/' + lang
        }
        return lang
    },
    getFlag(lang) {
      if (lang == "en") {
        return "gb";
      }else if(lang == 'ja') {
          return 'jp'
      }else if(lang == 'ja') {
          return 'jp'
      }
      return lang;
    },
  },
}
</script>

<style lang="scss" scoped>

</style>