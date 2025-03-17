<!-- src/App.vue -->
<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo
        :allMoviesCount="movies.length"
        :favouriteMoviesCount="movies.filter((ele) => ele.favourite).length"
      />
      <div class="search-panel">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList :movies="movies" @onToggle="onToggleHandler" @onRemove="onRemoveHandler" />
      <MovieAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>

<script lang="ts">
import AppInfo from './components/AppInfo.vue'
import SearchPanel from './components/SearchPanel.vue'
import AppFilter from './components/AppFilter.vue'
import MovieList from './components/MovieList.vue'
import MovieAddForm from './components/MovieAddForm.vue'

export default {
  name: 'App',
  components: {
    AppInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm,
  },
  data() {
    return {
      movies: [
        { id: 1, name: 'Omar', viewers: 811, favourite: false, like: true },
        { id: 2, name: 'Empire of Usman', viewers: 411, favourite: true, like: false },
        { id: 3, name: 'Ertuglur', viewers: 521, favourite: false, like: true },
      ],
    }
  },
  methods: {
    createMovie(item) {
      this.movies.push(item)
    },
    onToggleHandler({ id, prop }) {
      this.movies = this.movies.map((item) => {
        if (item.id === id) {
          return { ...item, [prop]: !item[prop] }
        }
        return item
      })
    },
    onRemoveHandler(id) {
      this.movies = this.movies.filter((item) => item.id !== id)
    },
    onFavouriteHandler(id) {
      console.log(id)
      this.movies = this.movies.map((item) => {
        if (item.id === id) {
          item.favourite = !item.favourite
        }
        return item
      })
    },
  },
}
</script>

<style></style>
