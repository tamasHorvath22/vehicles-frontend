<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <div v-for="(vehicle, index) in vehicles" :key = index>
        <div>{{ vehicle.make }}</div>
        <div>{{ vehicle.type }}</div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Vehicles',
  props: {},
  data () {
    return {
      title: 'Járművek',
      vehicles: []
    }
  },
  mounted () {
    axios
      .get('http://localhost:3001/vehicle/all')
      .then(response => (this.vehicles = JSON.parse(response.data)))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
