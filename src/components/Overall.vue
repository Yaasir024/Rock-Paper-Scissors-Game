<template>
<div class="overall">
      <h1 v-if="overallWinner == 'player'">
        YOU WIN <br />
        🎉🎉
      </h1>
      <h1 v-if="overallWinner == 'computer'">
        YOU LOSE <br />
        😞😞
      </h1>
      <p>{{ playerScore }} - {{ computerScore }}</p>
      <button class="try-again-btn" @click="$emit('resetGame')">Try Again</button>
    </div>
</template>

<script setup>
const emits = defineEmits(['resetGame'])
const props = defineProps(["playerScore", "computerScore", "overallWinner"]);
</script>
<style>
.overall {
  max-width: 650px;
  margin: 0 auto;
  text-align: center;
  padding: 30px 0;
}
.overall h1 {
  font-size: 60px;
}
.overall p {
  font-size: 40px;
}
.try-again-btn {
  outline: none;
  border: none;
  cursor: pointer;
  font-size: 1.5rem;
  margin-top: 15px;
  padding: 20px 50px;
  border-radius: 30px;
  position: relative;
  color: #fff;
  background: #222;
  transition: transform 0.3s ease;
}
.try-again-btn::after,
.try-again-btn::before {
  content: "";
  position: absolute;
  opacity: 0.2;
  background: #222;
  border-radius: inherit;
  width: 100%;
  height: 100%;
  left: 0;
  bottom: 0;
  z-index: -1;
  transition: transform 0.3s ease;
}
.try-again-btn:hover {
  transform: translate(-12px, -12px);
}
.try-again-btn:hover::after {
  transform: translate(7px, 7px);
}
.try-again-btn:hover::before {
  transform: translate(10px, 10px);
}
</style>
