<template>
  <div id="leaderboard">
    <h1>Masters 2017 Leaderboard Data</h1>
    <button v-on:click="getLeaderboard">Get Leaderboard</button>
    <button>Update Data</button>
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
      this.$http.get('static/leaderboard_legacy_data.json')
        .then(response => {
          this.playerList = response.body
          console.log(this.playerList)
        },
    response => { console.log('error lul') })
    }
    /*
    updateData: function () {
      $.ajax({
        url: '/static/getLeaderboard.py',
        success: function (response) {
          console.log('hey')
        }
      })
      */
  }
}

</script>

<style scoped>

#leaderboard {
  text-transform: uppercase;
  border: 1px solid black;
  padding: 20px;
  width: 50%;
	padding: 10px;
}

</style>
