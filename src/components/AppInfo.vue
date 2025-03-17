<template>
  <div class="app-info">
    <p class="fs-3 text-uppercase">All movies count:{{ allMoviesCount }}</p>
    <p class="fs-4 text-uppercase">Favourite movies count: {{ favouriteMoviesCount }}</p>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    allMoviesCount: { type: Number, required: true },
    favouriteMoviesCount: { type: Number, required: true },
  },
  name: 'AppInfo',
}
</script>
<style scoped>
.app-info {
  background-color: #fcfaf5;
  padding: 1.5rem;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
