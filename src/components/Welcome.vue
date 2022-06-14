<template>
  <main>
    <div class="nav">
      <RouterLink to="/about">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
          <!--! Font Awesome Pro 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. -->
          <path
            d="M64 192c27.25 0 51.75-11.5 69.25-29.75c15 54 64 93.75 122.8 93.75c70.75 0 127.1-57.25 127.1-128s-57.25-128-127.1-128c-50.38 0-93.63 29.38-114.5 71.75C124.1 47.75 96 32 64 32c0 33.37 17.12 62.75 43.13 80C81.13 129.3 64 158.6 64 192zM208 96h95.1C321.7 96 336 110.3 336 128h-160C176 110.3 190.3 96 208 96zM337.8 306.9L256 416L174.2 306.9C93.36 321.6 32 392.2 32 477.3c0 19.14 15.52 34.67 34.66 34.67H445.3c19.14 0 34.66-15.52 34.66-34.67C480 392.2 418.6 321.6 337.8 306.9z"
          /></svg
      ></RouterLink>
    </div>
    <h1>ROCK PAPER</h1>
    <h1>SCISSORS</h1>

    <div class="limits">
      <h3>Choose Your Limit</h3>

      <div class="buttons">
        <Button :content="10" style="margin-right: 10px"
        @click="$emit('start', 10)" />
        <Button :content="20" style="margin-right: 10px"
        @click="$emit('start', 20)" />
        <Button :content="30" @click="$emit('start', 30)" />
      </div>
    </div>
  </main>
</template>



<script setup>
import Button from "@/components/Button.vue";
const emits = defineEmits(['start'])
const confirm = () => {
  console.log('Confirm');
}
</script>

<style scoped>
.nav {
  display: flex;
  justify-content: flex-end;
}
.nav svg {
  fill: #fff;
  cursor: pointer;
  width: 20px;
}
main {
  text-align: center;
  height: 100vh;
}
h1 {
  font-size: 60px;
  background: linear-gradient(to right, #f32170, #ff6b08, #cf23cf, #eedd44);
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
}
.limits {
  margin-top: 40px;
}
.limits h3 {
  font-size: 20px;
}
.buttons {
  margin-top: 40px;
}
</style>
