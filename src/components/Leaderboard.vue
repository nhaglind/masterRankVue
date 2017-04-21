<template>
<div id="leaderboard">
  <button v-on:click="getLeaderboard">Get Leaderboard</button>
  <button v-on:click="updateData">Update Data</button>
  <table>
    <thead>
      <tr>
        <td>Player Name</td>
        <td>Player Score</td>
        <td>To Par</td>
      </tr>
    </thead>
    <tbody>
      <tr v-for="playerList in playerList">
        <td>{{ playerList.playerName }}</td>
        <td>{{ playerList.score }}</td>
        <td>{{ playerList.overUnder}}</td>
      </tr>
    </tbody>
  </table>
</div>
</template>

<script>

global.jQuery = require('jquery')
var $ = global.jQuery
window.$ = $

export default {
  name: 'Leaderboard',
  data: function () {
    return {
      playerList: [
        {playerName: 'Tiger Woods', score: 288, overUnder: -3}
      ]
    }
  },
  methods: {
    getLeaderboard: function () {
      this.$http.get('static/leaderboard_data.json')
        .then(response => {
          this.playerList = response.body
          console.log(this.playerList)
        },
    response => { console.log('error lul') })
    },
    updateData: function () {
      $.ajax({
        url: '/static/getLeaderboard.py',
        success: function (response) {
          console.log('hey')
        }
      })
    }
  }
}

</script>

<style scoped>

#leaderboard {
  margin: 0 auto;
  width: 500px;
  text-transform: uppercase;
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
