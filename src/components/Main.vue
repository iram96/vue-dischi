<template>
<main>
    <div class="container row ">
        
            

            <SongCard  />
           

        

    </div>

</main>
</template>

<script>

import SongCard from './SongCard.vue'

export default {
    name: 'Main',
    components: {
        SongCard,
    },
    props: ['disc'],
    
  
  
}
</script>

<style lang='scss' scoped>
main{
    background-color: #1E2D3B;
    height: 100vh;
    .container{
        max-width: 70%;
        margin: 0 auto;
        

    }
}
</style>