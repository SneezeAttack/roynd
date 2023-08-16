
<template>
<div class="host">
<h3>Characters in Star Wars</h3>


<div class="list">
	<span v-for="(entry, index) in data.results" class="details">
    <router-link :to="{ name: 'character', params: { id: index+1 } }">
		<img src='@/assets/SW.png' alt="SW" width="90" height="90" />
		<h3>{{entry.name}}</h3>
		<div>{{entry.gender}} | {{entry.birth_year}}</div>
		<img src='@/assets/icons/icon-forward.png' alt="select" class="forward" />
    </router-link>
	</span>
</div>
</div>
</template>

<script>


export default {
	data() {
		return {
			data: []
		}
	},
	mounted() {
		fetch('https://swapi.dev/api/people/?format=json')
		.then(res => res.json())
		.then(data => this.data = data)
		.catch(err => console.log(err.message))
	}
	
}
</script>

<style scoped>

.list{
	
	font-family: Montserrat;

	background-color: #19181E;
	background-image: linear-gradient(#5634A300,#702AEAFF);
}
span{
	
	background-color: #262638;
	box-shadow: 10px 10px #00000006;
}

.host{

	margin: 0px 0px;
}
/* CARD CSS STUFFS */


img{
	float:left;
	border-top-left-radius: 10px;
	border-bottom-left-radius: 10px;
	padding-right: 50px;
}
p, h3{
	margin: 0px;
	padding: 0px 10px;
}
span{
	list-style-type: none;
	background: #262638;
	margin: 20px 10px;
	border-radius: 10px;
	display: block;
	height: 90px;
	
	
}

.details div{

	padding-top: 20px;

	
}

.details h3{
	padding-top: 10px;
}

.forward{
	float: right;
	display:inline-block;

	padding-right: 10px;
	padding-bottom: 45px;
}

a{
  text-decoration: none;
  color: white;
}
</style>