<template>
  <aside class="sidebar">
    <h2>Cliked Squares</h2>
    <ol>
      <li v-for="(square, index) in clickedSquares" :key="index">
        {{ square }}
      </li>
    </ol>
  </aside>
</template>

<script setup>
defineProps({ clickedSquares: Array });
</script>

<style scoped>
.sidebar {
  width: 250px;
  padding: 1rem;
  border-left: 2px solid #ddd;
  background: tomato;
  color: white;
}

@media (max-width: 768px) {
  .sidebar {
    border-left: none;
    border-top: 2px solid #ddd;
    width: 100%;
  }
}
</style>
