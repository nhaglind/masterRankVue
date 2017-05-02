<template>
  <div id="playerpicks">
    <h1>Player Picks</h1>
    <button>Add Players</button>
    <button>Save List</button>
    <ul>
      <li>
        <label>Player Name</label><input></input>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Playerpicks'
}
</script>

<style scoped>

#playerpicks {
  text-transform: uppercase;
  border: 1px solid black;
  padding: 20px;
  width: 50%;
	padding: 10px;
  margin-left: 10px;
}

ul {
  list-style: none;
  text-align: left;
}

label {
  padding-right: 10px;
}

</style>
