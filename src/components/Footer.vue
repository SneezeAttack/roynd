<template>

<div class="footer">
	<span> <img src="@/assets/icons/icon-calendar.png" alt="homeImage" />Home</span>
	<span> <img src="@/assets/icons/Vector.png" alt="charImg" /> Characters</span>
	<span> <img src="@/assets/icons/icon-user.png" alt="settingsImg" />Settings</span>
</div>
</template>

<script>
export default {
	data() {
		return {
			homeImg: '@/assets/icons/icon-calendar.png',
			charImg: '@/assets/icons/Vector.png',
			settingsImg: '../assets/icons/icon-user.png'
		}
	}
}
</script>

<style scoped>

.footer{

	position: fixed;
	bottom: 0px;
	height: 150px;
	width: 100%;
	background-color: ##1D1B2B;
	margin: 0px;
	text-align: center;
	padding: 0;
	margin: 0;
}

.footer span{
	float:left;
	display:block;
	width: 32%;
	height: 150px;
	margin: 0px 0px;
	border: 1px solid white;
	background-color: #1D1B2B;

	
}

.footer span img{

	display:block;
	
	padding: 60px 0px 15px 55px;
}
</style>