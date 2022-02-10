<template>
  <header>
      <img src="../assets/logo.png" alt="">
  </header>
</template>

<script>
export default {
    name: 'Header',
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
        position: absolute;
        left: 5px;
        top: 5px
    }
}
</style>