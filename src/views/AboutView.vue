<template>
  <div class="about">
    <div class="nav">
      <RouterLink to="/">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M9.375 233.4l128-128c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25L109.3 224H480c17.69 0 32 14.31 32 32s-14.31 32-32 32H109.3l73.38 73.38c12.5 12.5 12.5 32.75 0 45.25c-12.49 12.49-32.74 12.51-45.25 0l-128-128C-3.125 266.1-3.125 245.9 9.375 233.4z"/></svg></RouterLink>
    </div>
    <div class="content">
      <h2>Thanks for playing Rock Paper Scissors. This game was made by Falana Yaasir. A Junior Developer</h2>
      <h1>How the game Works</h1>
      <img src="../assets/rock-paper-scissors 3.jpg" alt="">
      <h2>Rock beats Scissors</h2>
      <h2>Paper beats Rock</h2>
      <h2>Scissors beats Paper</h2>
    </div>
  </div>
</template>

<style scoped>
.nav {
  display: flex;
  justify-content: flex-start;
}
.nav svg {
  fill: #fff;
  cursor: pointer;
  width: 20px;
}
.content {
  max-width: 720px;
  margin: 0 auto;
  text-align: center;
  padding-top: 50px;
}
</style>

