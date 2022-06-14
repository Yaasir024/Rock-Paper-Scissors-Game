<script>
export default {
  props: ["content"],
  setup() {},
};
</script>

<template>
  <button class="btn">{{ content }}</button>
</template>

<style scoped>
.btn {
  outline: none;
  border: none;
  cursor: pointer;
  font-size: 1.5rem;
  padding: 25px 60px;
  position: relative;
  color: #fff;
  background: none;
  transition: transform 0.3s ease;
}
.btn::after,
.btn::before {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  z-index: -1;
  border: 4px solid;
  border-image-slice: 1;
  border-width: 5px;
  border-image-source: linear-gradient(to left, #f32170, #ff6b08, #cf23cf);
  width: calc(100% - 8px);
  height: calc(100% - 8px);
  transition: transform 0.3s ease;
}
.btn:hover::after {
  transform: translate(-7px, -7px);
}
.btn:hover::before {
  transform: translate(7px, 7px);
}
</style>
