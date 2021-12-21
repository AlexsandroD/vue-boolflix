<template>
  <header>
    <div class="container-80">
      <div class="logo">
        <img
          src="https://fontmeme.com/permalink/211221/0a43aa36584f2895324a0006b42b5d1a.png"
          alt=""
        />
      </div>
      <form @submit.prevent="$emit('search', inputSearch)">
        <button><i class="fas fa-search"></i></button>
        <input type="text" v-model="inputSearch" />
      </form>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      inputSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped>
header {
  form{
    position: relative;
  }
  height: 60px;
  background-color: #181818;
  .container-80{
    width: 90%;
    margin: auto;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-content: center;
    
    .logo{
      display: flex;
      width: 200px;
      img{
        width: 100%;
      }
    }
    form{
      line-height: 60px;
    }
  }
}
</style>
