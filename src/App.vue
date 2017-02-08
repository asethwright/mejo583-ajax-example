<template>
  <div id="app">
    <Player v-for="player in players" :player="player"></Player>
  </div>
</template>

<script>
import axios from 'axios'
import Player from './components/Player'

export default {
  name: 'app',

  components: {
    Player
  },

  data () {
    return {
      players: []
    }
  },

  mounted () {
    axios.get('/static/basketball.json')
      .then((response) => {
        console.log(response.data)
        this.players = response.data
      })
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
