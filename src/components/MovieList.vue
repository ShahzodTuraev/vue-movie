<template>
  <div class="movie-list list-group">
    <ul>
      <MovieListItem
        v-for="movie in movies"
        :key="movie.id"
        :movie="movie"
        @onToggle="$emit('onToggle', $event)"
        @onRemove="$emit('onRemove', $event)"
      />
    </ul>
  </div>
</template>
<script lang="ts">
import MovieListItem from './MovieListItem.vue'
export default {
  name: 'MovieList',
  components: { MovieListItem },
  props: { movies: { type: Array, required: true } },
}
</script>
<style scoped>
.movie-list {
  margin-top: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
