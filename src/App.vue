<template>
  <div class="app">
    <div class="content-wrapper">
      <Chessboard @squareClick="handleClick" />

      <Sidepanel :clickedSquares="clickedList" @clear="clearList" />
    </div>
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
/* .app {
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
} */

.app {
  display: flex;
  justify-content: center; /* Center the wrapper */
  padding: 1rem;
}

.content-wrapper {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 1000px;
  width: 100%;
}

@media (max-width: 968px) {
  .content-wrapper {
    flex-direction: column;
    align-items: center;
  }

  .content-wrapper .sidebar {
    border-left: none;
    border-top: 2px solid #ddd;
    width: 100%;
    max-width: 600px;
  }
}
</style>
