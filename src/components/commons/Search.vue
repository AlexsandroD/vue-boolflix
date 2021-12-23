<template>
  <div class="search">
    <!-- <h3>Films</h3> -->
    <div class="container-70">
      <ul>
        <li v-for='(film, index) in filmsInput' :key="index">
            <div class="container-li">
                <img :src="`${getImg(film.poster_path)}`" :alt="film.title + ' poster ' ">
                <div class="text">
                    <h4>Titolo: {{film.title}}</h4>
                    <p v-if="film.title != film.original_title" >Titolo originale:{{film.original_title}}</p>
                    <p v-else></p>
                    <p>Trama:{{film.overview}}</p>
                    <div>Voto:<span>{{star(film.vote_average)}}</span></div> 
                    <span><img :src="`https://flagcdn.com/16x12/${getFlag(film.original_language)}.png`">
                    </span> 
                </div>
            </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Search",
  props: {
    filmsInput: Array,
  },
  data() {
    return {
      voteFilm: 0,
      
    };
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
      }
      return lang;
    },
  },
};
</script>

<style lang="scss" scoped>

</style>
