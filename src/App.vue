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
  margin-top: 10px;
  display: -ms-flex;
	display: -webkit-flex;
	display: flex;
}

button:hover {
  cursor: pointer;
}

tr {
  text-align: left;
}

td {
  min-width: 200px;
}

button {
  display: inline;
  background: black;
  color: white;
  text-transform: uppercase;
  border: 2px solid black;
  padding: 10px;
  margin: 0 0 20px 0px
}

button:hover {
  background: white;
  color: black;
}

</style>
