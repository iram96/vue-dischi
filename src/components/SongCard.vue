<template>
  
      <div class="song-card m-4 col-2 p-4">
            
                
            <img  :src="disc.poster" :alt="disc.title">
            
            <h4 class="font-white">{{ disc.title}}</h4>
            <span class="font-14">{{disc.author}}</span>
            <span class="font-14">{{disc.year}}</span>
        </div>
    
        
    
   
  
</template>

<script>
export default {
    name: 'musicCard',
    props: ['disc']

}
</script>

<style scoped lang='scss'>
.song-card{
    background-color: #2E3A46;
    text-align: center;
    color: white;
    img{
        width: 70px;
        display: block;
        margin: 0 auto
    }
}


</style>