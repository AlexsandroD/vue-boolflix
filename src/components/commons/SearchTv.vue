<template>
    <div class="search">
        <h3>serie tv</h3>
        <div class="container-80">
            <ul>
                <li v-for='(show, index) in shows' :key="index"><img :src="`${getImg(show.backdrop_path)}`" alt="Immagine non disponibile">{{show.name}},{{show.original_title}},Voto:{{show.vote_average}}<span><img :src="`https://flagcdn.com/16x12/${getFlag(show.original_language)}.png`"></span> </li>
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
    getImg(lang){
        if(lang == null){
          lang = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT1j5dT8vlJwX_nr02NYSRfsr_pH4fyaxIqFw&usqp=CAU';
        }else{
            lang = 'http://image.tmdb.org/t/p/w300/' + lang
        }
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
.container-80{
    width: 70%;
    margin: 50px auto;
        ul{
            display: grid;
            justify-content: center;
            grid-template-columns:repeat(auto-fill, 200px);
            column-gap:30px;
            row-gap: 20px;
            li{
                img{
                    width: 100%;
                }
                span{
                    img{
                        width: 16px;
                        height: 12px;
                    }
                }
            }
        }
    }

  
</style>