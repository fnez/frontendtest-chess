<template>
  <div class="chessboard">
    <!-- 8 * 8 grid -->
    <div class="row" v-for="(row, rowIndex) in 8" :key="rowIndex">
      <div class="square" v-for="(column, columnIndex) in 8" :key="columnIndex">
        {{ squareLabel(rowIndex, columnIndex) }}
      </div>
    </div>
  </div>
</template>

<script setup>
const squareLabel = (row, column) => {
  const columns = "abcdefgh";
  return columns[column] + (8 - row);
};
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
