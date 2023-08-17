<template>
<div class="main" v-if="person">
  
  <span class="center">
    <h3>{{person.name}}</h3>

    <img src="@/assets/SW.png" alt="SW image" />
    <div>{{person.gender}} | {{person.birth_year}}</div>
  </span>
  
  
  
  <div class="details">
    <h3>Planet</h3>

    <div>
      <p class="left">Home planet:</p> <p class="right">{{planet.name}}</p>
    </div>
    <div class="clear"></div>

    <div>
      <p class="left">Rotation period:</p>
      <p class="right">{{planet.rotation_period}}</p>
    </div>
    <div class="clear"></div>

    <div>
      <p class="left">Population:</p>
      <p class="right">{{planet.population}}</p>
    </div>
    <div class="clear"></div>

    
    
  
  <h3>Starships</h3>

    <div v-if="starships.length > 0">
    <div v-for="ship in starships">
      <p class="left">Name:</p>
      <p class="right">{{ship.name}}</p>

      <div class="clear"></div>

      
      <div>
        <p class="left">Model:</p>
        <p class="right">{{ship.model}}</p>
      </div>
      <div class="clear"></div>

      
      <div>
        <p class="left">Manufacturer:</p>
        <p class="right">{{ship.manufacturer}}</p>
      </div>
      <div class="clear"></div>
      <hr />
    </div>
    </div>
    
    
    <div v-else style="text-align: center">

      <h3>No starships on record</h3>
      
    </div>
  </div>
  
</div>
</template>

<script>
  export default {
    data() {
      return {
        person: [],
        planet: [],
        starships: [],
        id: this.$route.params.id,
      }
    },
  computed: {},
  methods: {

    getData: function(p){

    fetch(p.homeworld + '?format=json')
    .then(res => res.json())
    .then(data => this.planet = data)
    .catch(err => console.log(err.message))

  
    for(let i = 0; i < p.starships.length; i++){
      fetch(p.starships[i] + '?format=json')
      .then(res => res.json())
      .then(data => {this.starships.push(data); console.log(data)})
      .catch(err => console.log(err.message))
    }
  }


  },

  mounted() {
    fetch('https://swapi.dev/api/people/'+this.id+'?format=json')
    .then(res => res.json())
    .then(data => {this.person = data; this.getData(this.person)})
    .catch(err => console.log(err.message))
    
  }
}
</script>

<style scoped>

.main{

  padding: 0px 15px 0px 15px;
  
  min-height: 900px;/*Footer blocks starship details if not set*/

}

.center{
	text-align:center;
  display: block;
}


.right{

  float: right;

}

.left{

  float: left;

}

.clear{

  clear: both;
  
}

</style>