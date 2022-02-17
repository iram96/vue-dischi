<template>
  <header class="row justify-content-between">
    <div class="col-1 justify-content-center">
      <img src="../assets/logo.png" alt="" />
    </div>
    <div class="col-4 px-4">
      <Select :genre-list="genreList" @searched-genre="getGenre" />
    </div>
  </header>
</template>

<script>
import Select from "./Select.vue";

export default {
  name: "Header",
  components: {
    Select,
  },
  data() {
    return {
      selectedGenre: "",
    };
  },
  props: ["genreList"],
  methods: {
    reassignValue(genre) {
      this.selectedGenre = genre;
    },
    getGenre(item) {
      this.reassignValue(item);
      console.log(this.selectedGenre);
      this.$emit("user-genre", this.selectedGenre);
    },
  },
};
</script>

<style lang='scss' scoped>
header {
  background-color: #2e3a46;
  height: 50px;

  position: relative;
  img {
    height: 40px;
    width: 40px;
  }
}
</style>