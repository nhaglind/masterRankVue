<template>
  <div id="app">
    <img src="./assets/logo.png">
    <leaderboard></leaderboard>
  </div>
</template>

<script>
import Leaderboard from './components/Leaderboard'

export default {
  name: 'app',
  components: {
    Leaderboard
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
