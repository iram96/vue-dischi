<template>
  <div id="app">
    <Header />
    <Main />
    
  </div>
</template>

<script>

import Header from './components/Header.vue'
import Main from './components/Main.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
      return {
        discsList: []
  
      }
  },
  methods: {
    getDiskImg(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music').then( res => {
        this.discsList = res.data.response;
        console.log(this.discsList);

      })
    }
  },
  mounted() {
    this.getDiskImg()
    
  },
  computed: {

  }

  
}
</script>

<style lang="scss">
@import "./assets/sass/style.scss";

  *{
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
.clearfix:after{                         
  display: table;
  content: "";
  clear: both;
}

body{
  // max-width: 1200px;
  margin: 0 auto;
}
}

</style>
