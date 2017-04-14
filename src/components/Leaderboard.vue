<template>
  <div id="leaderboard">
    <li v-for="playerList in playerList">
      Player Name: {{ playerList.playerName }}
      Total Score: {{ playerList.score }}
    </li>
    <button v-on:click="getLeaderboard">Get Leaderboard</button>
  </div>
</template>

<script>
export default {
  name: 'Leaderboard',
  data: function () {
    return {
      playerList: [
        {name: 'Tiger Woods', score: 288}
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
    }
  }
}
</script>

<style scoped>
li {
  list-style: none;
}
</style>
