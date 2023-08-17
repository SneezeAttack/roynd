<template>

<div class="footer">

  <span> <img src="@/assets/icons/icon-calendar.png" alt="homeImage" />Home</span><!--Home does not exist-->
  
  <router-link :to="{ name: 'List' }" >
    <span> <img src="@/assets/icons/Vector.png" alt="charImg" /> Characters</span>
  </router-link>
  
	<span> <img src="@/assets/icons/icon-user.png" alt="settingsImg" />Settings</span>
  <!--Settings does not exist-->
  
</div>
</template>

<script>

export default {}

</script>

<style scoped>

  .footer{

  position: fixed;
  bottom: 0px;
  height: 150px;
  width: 100%;
  background-color: ##1D1B2B;
  margin: 0px 0px;
  text-align: center;
  padding: 0px 0px;
  margin: 0;
  }

  .footer span{

  float:left;
  display:block;
  width: 33.3%;
  height: 150px;
  margin: 0px 0px;
  border: 0px solid white;
  background-color: #1D1B2B;

  }

  .footer span img{

  display:block;

  padding: 60px 0px 15px 55px;

  }

  a{

  text-decoration: none;
  color: white;

  }
</style>