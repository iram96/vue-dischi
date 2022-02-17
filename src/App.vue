<template>
  <div id="app">
    <Header :genre-list="genreList" @user-genre="setCurrentGenre" />
    <Main :discs-list="discsList" :current-genre="currentGenre" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data() {
    return {
      discsList: [],
      genreList: [],
      currentGenre: [],
    };
  },
  methods: {
    getDiskImg() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.discsList = res.data.response;
          console.log(this.discsList);
          this.discsList.forEach((disc) => {
            if (!this.genreList.includes(disc["genre"])) {
              this.genreList.push(disc.genre);
            }
            console.log(this.genreList);
          });
        });
    },
    setCurrentGenre(item) {
      this.currentGenre = item;
      console.log(this.currentGenre);
    },
  },
  mounted() {
    this.getDiskImg();
  },
};
</script>

<style lang="scss">
@import "./assets/sass/style.scss";

* {
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  .clearfix:after {
    display: table;
    content: "";
    clear: both;
  }

  body {
    // max-width: 1200px;
    margin: 0 auto;
  }
}
</style>
