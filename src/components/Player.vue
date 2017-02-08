<template>
  <div class="Player">
    <h3>{{ player.first }} {{ player.last }}</h3>
    <p>{{ shootingPct }}</p>
  </div>
</template>

<script>
export default {
  props: [
    'player'
  ],

  computed: {
    shootingPct () {
      return this.player.fieldGoals / this.player.fieldGoalsAttempted
    }
  }
}
</script>

<style scoped>
.Player {
}
</style>
