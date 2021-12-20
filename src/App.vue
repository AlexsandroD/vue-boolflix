<template>
  <div id="app">
   <Header/>
   <Main/>
  </div>
</template>

<script>
import Main from "./components/macros/Main.vue";
import Header from"./components/macros/Header.vue";
export default {
  name: "App",
  components: {
    Main,
    Header
  },
};
</script>

<style lang="scss">
@import './assets/global.scss';
#app {
 
}
</style>
