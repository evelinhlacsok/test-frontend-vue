<template>
  <div id="app">
    <Header msg="Welcome to Your Vue.js App"/>
    <Cards></Cards>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Cards from './components/Cards.vue'

export default {
  name: 'app',
  components: {
    Header,
    Cards
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
