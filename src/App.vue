<template>
  <div id="app">
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data() {
    return {
      name: ''
    }
  },
  created() {
    this.getHome()
  },
  methods: {
    getHome() {
      axios.get('http://121.4.255.180:3000/api/home').then(({ data: { name } }) => {
        this.name = name
      })
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
