<template>
  <div class="score-board">
    <div class="player">
      <h2>Player</h2>
      <p class="scores">
        <span>{{ playerScore }}</span>
        / <span>{{ limit }}</span>
      </p>
    </div>
    <div class="computer">
      <h2>Computer</h2>
      <p class="scores">
        <span>{{ computerScore }}</span>
        / <span>{{ limit }}</span>
      </p>
    </div>
  </div>
</template>

<script setup>
const props = defineProps(["playerScore", "computerScore", "limit"]);
</script>

<style scoped>
.score-board {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px;
}
.score-board .scores {
  font-size: 40px;
}
</style>
