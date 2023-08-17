<template>

<div class="background">
    <div class="back">
      
      <img src="@/assets/icons/icon-back.png" alt="Go back" @click="this.$router.go(-1)"/>
    </div>
    
  </div>


</template>

<script>
export default {}
</script>

<style scoped>

  .background{

    background-color: #19181E;
  
    font-size: 16px;
    font-family: Montserrat;
    padding-bottom: 10px;
  }

  .back{

    padding: 15px 0px 0px 30px;
    height: 46px;
    
  }
  
 
</style>