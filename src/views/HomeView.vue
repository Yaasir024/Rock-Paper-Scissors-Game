<script setup>
import Player from "@/components/Player.vue";
import Welcome from "@/components/Welcome.vue";
import ScoreBoard from "@/components/ScoreBoard.vue";
import Result from "@/components/Result.vue";
import Overall from "@/components/Overall.vue";
import { ref, reactive } from "vue";

const view = ref("welcome");
const limit = ref(10);
const choices = ref(["rock", "paper", "scissors"]);
const playerChoice = ref("");
const computerChoice = ref("");
const winner = ref("");
const overallWinner = ref("");
const playerScore = ref(0);
const computerScore = ref(0);

const startGame = (value) => {
  view.value = "player";
  limit.value = value;
};

const reset = () => {
  view.value = "welcome";
  playerChoice.value = "";
  computerChoice.value = "";
  winner.value = "";
  overallWinner.value = "";
  playerScore.value = 0;
  computerScore.value = 0;
};

const registerChoice = (value) => {
  playerChoice.value = value;
  getComputerChoice();
};

const getComputerChoice = () => {
  const random = Math.floor(Math.random() * 3);
  computerChoice.value = choices.value[random];

  evaluateScore();
};

const evaluateScore = () => {
  if (playerChoice.value == "rock" && computerChoice.value == "paper") {
    winner.value = "computer";
  }
  if (playerChoice.value == "rock" && computerChoice.value == "scissors") {
    winner.value = "player";
  } else if (playerChoice.value == "paper" && computerChoice.value == "rock") {
    winner.value = "player";
  } else if (
    playerChoice.value == "paper" &&
    computerChoice.value == "scissors"
  ) {
    winner.value = "computer";
  } else if (
    playerChoice.value == "scissors" &&
    computerChoice.value == "rock"
  ) {
    winner.value = "computer";
  } else if (
    playerChoice.value == "scissors" &&
    computerChoice.value == "paper"
  ) {
    winner.value = "player";
  } else if (playerChoice.value == computerChoice.value) {
    winner.value = "draw";
  }
  updateScore();
};
const updateScore = () => {
  if (winner.value == "player") {
    playerScore.value++;
  } else if (winner.value == "computer") {
    computerScore.value++;
  }
  view.value = "result";
  setTimeout(nextRound, 1500);
};

const nextRound = () => {
  if (playerScore.value == limit.value) {
    overallWinner.value = "player";
    view.value = "overall";
  } else if (computerScore.value == limit.value) {
    overallWinner.value = "computer";
    view.value = "overall";
  } else {
    view.value = "player";
  }
};
</script>

<template>
  <main>
    <Welcome @start="startGame" v-if="view == 'welcome'" />
    <ScoreBoard
      :playerScore="playerScore"
      :computerScore="computerScore"
      :limit="limit"
    />

    <Player
      v-if="view == 'player'"
      @registerChoice="registerChoice"
      @resetGame="reset"
    />

    <Result
      :playerChoice="playerChoice"
      :computerChoice="computerChoice"
      :winner="winner"
      v-if="view == 'result'"
    />
    <Overall
      @resetGame="reset"
      :playerScore="playerScore"
      :computerScore="computerScore"
      :overallWinner="overallWinner"
      v-if="view == 'overall'"
    />
  </main>
</template>
