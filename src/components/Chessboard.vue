<template>
  <div class="chessboard">
    <!-- 8 * 8 grid -->
    <div class="row" v-for="(row, rowIndex) in 8" :key="rowIndex">
      <div
        v-for="(column, colIndex) in 8"
        class="square"
        :class="{ highlighted: isClicked(rowIndex, colIndex) }"
        :key="colIndex"
        @click="handleClick(rowIndex, colIndex)"
      >
        {{ squareLabel(rowIndex, colIndex) }}
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
const highlighted = ref([]);

const handleClick = (row, col) => {
  const square = squareLabel(row, col);
  highlighted.value.push(square);
  emit("squareClick", square);
};

const isClicked = (row, col) => {
  return highlighted.value.includes(squareLabel(row, col));
};

const squareLabel = (row, column) => {
  const columns = "abcdefgh";
  return columns[column] + (8 - row);
};

const emit = defineEmits([["squareClick"]]);
</script>

<style>
.chessboard {
  display: grid;
  grid-template-rows: repeat(8, 1fr);
  aspect-ratio: 1 / 1;
  width: 100%;
  max-width: 600px;
  border: 2px solid gray;
}

.row {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
}

.square {
  display: flex;
  justify-content: center;
  align-items: center;
  aspect-ratio: 1;
  border: 1px solid lightblue;
  font-size: 16px;
  cursor: pointer;
}

.highlighted {
  background-color: yellow;
}
</style>
