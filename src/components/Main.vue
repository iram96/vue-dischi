<template>
  <main>
    <div class="container row">
      <SongCard
        v-for="disc in discsList"
        :key="disc.title"
        :disc="disc"
        :current-genre="currentGenre"
      />
    </div>
  </main>
</template>

<script>
import SongCard from "./SongCard.vue";

export default {
  name: "Main",
  components: {
    SongCard,
  },
  props: ["discsList", "currentGenre"],
};
</script>

<style lang='scss' scoped>
main {
  background-color: #1e2d3b;
  height: 100vh;
  .container {
    max-width: 70%;
    margin: 0 auto;
  }
}
</style>