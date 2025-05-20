<template>
  <div class="app">
    <div class="boardContainer">
      <Chessboard />
    </div>
    <!-- <Sidepanel /> -->
  </div>
</template>

<script setup>
import Chessboard from "./components/Chessboard.vue";

const handleClick = (square) => {
  console.log(square);
};
</script>
