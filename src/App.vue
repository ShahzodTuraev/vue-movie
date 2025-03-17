<!-- src/App.vue -->
<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo />
      <div class="search-panel">
        <SearchPanel />
        <AppFilter />
      </div>
      <MovieList />
      <MovieAddForm />
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
}
</script>

<style></style>
