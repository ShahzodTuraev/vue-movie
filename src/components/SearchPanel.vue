<template>
  <input type="text" class="form-control search-input" placeholder="search movie" />
</template>
<script lang="ts">
export default {
  name: 'SearchPanel',
}
</script>
<style scoped>
.search-input {
  margin-top: 2rem;
  margin-bottom: 1rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
