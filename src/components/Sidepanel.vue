<template>
  <aside class="sidebar">
    <h2>Cliked Squares</h2>

    <ol>
      <li v-for="(square, index) in clickedSquares" :key="index">
        {{ square }}
      </li>
    </ol>
    <button @click="clearSquares" class="clear-btn">Clear Squares</button>
  </aside>
</template>

<script setup>
defineProps({ clickedSquares: Array });
const emit = defineEmits(["clear"]);

const clearSquares = () => {
  emit("clear");
};
</script>

<style scoped>
.sidebar {
  width: 250px;
  padding: 1rem;
  border-left: 2px solid #ddd;
  background: tomato;
  color: white;
}

.clear-btn {
  margin-top: auto;
  padding: 0.5rem 1rem;
  background: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

@media (max-width: 768px) {
  .sidebar {
    border-left: none;
    border-top: 2px solid #ddd;
    width: 100%;
  }
}
</style>
