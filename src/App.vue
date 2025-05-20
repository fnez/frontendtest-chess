<template>
  <div class="app">
    <div class="boardContainer">
      <Chessboard @squareClick="handleClick" />
    </div>
    <Sidepanel :clickedSquares="clickedList" @clear="clearList" />
  </div>
</template>

<script setup>
import { ref } from "vue";
import Chessboard from "./components/Chessboard.vue";
import Sidepanel from "./components/Sidepanel.vue";

const clickedList = ref([]);

const handleClick = (square) => {
  clickedList.value.push(square);
};

const clearList = () => {
  clickedList.value = [];
};
</script>

<style>
.app {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.boardContainer {
  min-width: 50%;
}

.chessboard-container {
  flex: 1;
  min-width: 300px;
}

@media (max-width: 768px) {
  .boardContainer {
    min-width: 100%;
    display: flex;
    align-self: center;
    justify-content: center;
  }
}
</style>
