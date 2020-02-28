<template>
  <div id="app">
    <card :planet="planet"/>
    <button class="btn-next" @click="getRandomPlanet">Next</button>
  </div>
</template>

<script>
import card from './components/card.vue';
export default {
  name: 'App',
  components:{card},
  data(){
    return{
      planet: {},
    }
  },
  methods:{
    getRandomPlanet(){
      let planetNumber = Math.floor(Math.random() * (61 - 1)) + 1;
      this.$http.get('/planets/'+planetNumber).then(res => {
        this.planet = 
        { 
          name: res.data.name, 
          population: res.data.population,
          climate: res.data.climate, 
          terrain: res.data.terrain, 
          featured: (res.data.films).length
        }
      })
    }
  },
  created(){
    this.getRandomPlanet()
  }
}
</script>

<style>
html,body{
  margin:0;
  padding:0;
  height: 100%;
  width: 100%;
  font-family: 'Open Sans';
}

#app{
  height: inherit;
  background: repeat url('https://unblast.com/wp-content/uploads/2018/10/Sky-Stars-Pattern.jpg');
  background-size: 500px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

#app .btn-next{
  padding:15px 50px;
  border: 3px solid #fff;
  background-color:transparent;
  border-radius:10px;
  margin-top:20px;
  color:#fff;
  font-size:20px;
  font-weight: bold;
  text-transform: uppercase;
  cursor: pointer;
  transition: 0.3s;
}

#app .btn-next:focus{outline: 0}

#app .btn-next:hover{
  background-color:#fff;
  color:#000;
  transition: 0.3s;
}

</style>
