<template>
  <div class="song-card col-3 p-4" :class="{ 'd-none ': flagGenre() }">
    <div class="bgc-darkgray p-4">
      <img :src="disc.poster" :alt="disc.title" />

      <h4 class="font-white">{{ disc.title }}</h4>
      <span class="font-14 text-center d-block my-3">{{ disc.author }}</span>
      <span class="font-14 text-center d-block my-3">{{ disc.year }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "SongCard",
  props: ["disc", "currentGenre"],
  methods: {
    flagGenre() {
      if (this.disc.genre !== this.currentGenre) {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style scoped lang='scss'>
.song-card {
  background-color: #1e2d3b;
  text-align: center;
  color: white;
  .bgc-darkgray {
    background-color: #2e3a46;
    min-height: 300px;
  }
  img {
    width: 70px;
    display: block;
    margin: 0 auto;
  }
}
</style>