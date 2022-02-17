<template>
  <select v-model="optionSelected" @change="emitGenre" class="form-select">
    <option selected>Choose Genre</option>
    <option v-for="(genre, index) in genreList" :key="index" :value="genre">
      {{ genre }}
    </option>
  </select>
</template>

<script>
export default {
  name: "Select",
  props: ["genreList"],
  data() {
    return {
      optionSelected: "",
    };
  },
  methods: {
    emitGenre() {
      this.$emit("searched-genre", this.optionSelected);
    },
  },
};
</script>

<style>
</style>