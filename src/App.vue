<template>
  <div id="app">
    <h2>主人晚上好啊!!!！</h2>
    <h1>{{ name }}=={{ index }}</h1>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data() {
    return {
      name: '',
      index: ''
    }
  },
  created() {
    this.getHome()
    this.getIndex()
  },
  methods: {
    getHome() {
      axios.get('http://121.4.255.180:3000/api/home').then(({ data: { name } }) => {
        this.name = name
      })
    },
    getIndex() {
      axios.get('http://121.4.255.180:3000/api/index').then(({ data: { index } }) => {
        console.log('index=>', index)
        this.index = index
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
