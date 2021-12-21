<template>
  <header>
    <div class="logo">
      <img
        src="https://fontmeme.com/permalink/211221/0a43aa36584f2895324a0006b42b5d1a.png"
        alt=""
      />
    </div>
    <form @submit.prevent="$emit('search', inputSearch)">
      <input type="text" v-model="inputSearch" />
      <button>Click me</button>
    </form>
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
  height: 100px;
  background-color: black;
}
</style>
