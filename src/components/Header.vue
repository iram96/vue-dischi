<template>
  <header class="row justify-content-between">
      <div class="col-1 justify-content-center">

      <img src="../assets/logo.png" alt="">

      </div>
      <div class="col-4 px-4 ">
          <Select />


      </div>
  </header>
</template>

<script>
import Select from "./Select.vue";

export default {
    name: 'Header',
    components: {
        Select,
    }
}
</script>

<style lang='scss' scoped>
header{
    background-color: #2E3A46;
    height: 50px;
    
    position: relative;
    img{
        height: 40px;
        width: 40px;
        
    }
}
</style>