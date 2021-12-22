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
        <button @mouseenter="openBar()"><i class="fas fa-search"></i></button>
        <input
          type="text"
          :class="searchIcon == true ? 'active-input' : ''"
          v-model="inputSearch"
        />
        <div
          @click="closeBar()"
          class="close"
          :class="closeIcon == true ? 'active-show' : ''"
        >
          <i class="fas fa-times"></i>
        </div>
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
      searchIcon: false,
      closeIcon: false,
    };
  },
  methods: {
    openBar() {
      this.searchIcon = true;
      this.closeIcon = true;
    },
    closeBar() {
      this.searchIcon = false;
      this.closeIcon = false;
      this.inputSearch = ''
    },
  },
};
</script>

<style lang="scss" scoped>
header {
  display: flex;
  align-items: center;
  padding-top:20px;
  form {
    position: relative;
    display: flex;
    align-items: center;
    input {
      width: 0;
      color: white;
      background-color: #181818;
      border: none;
      transition: ease 0.6s;
    }
    button {
      font-size: 20px;
      color: white;
      background-color: #181818;
      box-shadow: none;
      border: none;
      margin-right: 10px;
    }

    .close {
      display: none;
      color: white;
      font-size: 20px;

    }
    .active-input {
      width: 300px;
      border: 1px solid white;
      height: 30px;
      transition: ease 0.3s;
    }
    .active-show {
      display: inline-block;
      margin-left: 10px;
    }
  }
  height: 60px;
  background-color: #181818;
  .container-80 {
    width: 90%;
    margin: auto;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-content: center;

    .logo {
      display: flex;
      width: 200px;
      img {
        width: 100%;
      }
    }
  }
}
</style>
