<template>
<main>
    <div class="container row justify-content-around">
        
            <SongCard v-for='disc in discsList' :key='disc.title' :disc='disc' />

        

    </div>

</main>
</template>

<script>
import axios from 'axios';
import SongCard from './SongCard.vue'

export default {
    name: 'Main',
    components: {
        SongCard,
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

      })
    }
  },
  mounted() {
    this.getDiskImg()
    console.log(this.discsList)
  }

}
</script>

<style lang='scss' scoped>
main{
    background-color: #1E2D3B;
    height: 100vh;
    .container{
        max-width: 70%;
        margin: 0 auto

    }
}
</style>