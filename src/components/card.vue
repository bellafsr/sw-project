<template>
  <div class="card">
    <h1>{{planet.name}}</h1>
    <hr>
    <div class="generalInfo">
      <h2>Population: {{planet.population}}</h2>
      <h2>Climate: {{planet.climate}}</h2>
      <h2>Terrain: {{planet.terrain}}</h2>
    </div>
    <h4>Featured in {{planet.featured}} films </h4>
  </div>
</template>

<script>
export default {
  props:{planet: Object}
}
</script>

<style scoped>

.card{
  width: 25%;
  min-width: 322px;
  height: 72%;
  min-height:600px; 
  border: 5px solid #DDC706;
  background-color: rgba(0, 0, 0, 0.61);
  color: #DDC706;
  display: flex;
  flex-direction: column;
}
.card h1{
  font-size:2.5rem;
}
.card .generalInfo h2{
  font-size:1.5rem
}

.card h4{
  flex: 1 1 auto;
  font-size:1rem;
  margin: 0px;
  padding:0px;
}
.card h1, 
.card h4{
  text-align: center;
}

.card hr{
  background-color:#DDC706;
  border: none;
  height: 5px;
  margin:0px;
}
.card .generalInfo{
  flex: 2 1 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 0 10%;
}

</style>