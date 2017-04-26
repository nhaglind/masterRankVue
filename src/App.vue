<template>
  <div id="app">
    <leaderboard></leaderboard>
    <playerpicks></playerpicks>
  </div>
</template>

<script>

import Leaderboard from './components/Leaderboard'
import Playerpicks from './components/Playerpicks'

export default {
  name: 'App',
  components: {
    Leaderboard,
    Playerpicks
  }
}
</script>

<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 60px;
  display: -ms-flex;
	display: -webkit-flex;
	display: flex;
}
</style>
