<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Vehicles/>
    <button @click="click">Button</button>
  </div>
</template>

<script>
import Vehicles from './components/Vehicles.vue'
import axios from 'axios'

export default {
  name: 'app',
  components: {
    Vehicles
  },
  methods: {
    click () {
      axios
        .get('http://localhost:3001/vehicle/all')
        .then(response => (console.log(JSON.parse(response.data))))
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
