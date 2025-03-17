<template>
  <div class="movie-add-form">
    <h3>Add new movie</h3>
    <form class="add-form d-flex" @submit.prevent>
      <input
        type="text"
        class="form-control new-movie-label"
        :value="name"
        @input="name = $event.target.value"
        placeholder="Movie name?"
      />
      <input
        type="number"
        class="form-control new-movie-label"
        :value="viewers"
        @input="viewers = $event.target.value"
        placeholder="How many viewed?"
      />
      <button @click="addMovie" class="btn btn-outline-dark" type="submit">Add</button>
    </form>
  </div>
</template>
<script lang="ts">
export default {
  name: 'MovieAppForm',
  data() {
    return {
      name: '',
      viewers: '',
    }
  },
  methods: {
    addMovie() {
      if (!this.name || !this.viewers) return
      const newMovie = {
        id: Date.now(),
        name: this.name,
        viewers: this.viewers,
        favourite: false,
        like: false,
      }
      this.$emit('createMovie', newMovie)
      this.name = ''
      this.viewers = ''
    },
  },
}
</script>
<style scoped>
.movie-add-form {
  margin-top: 2rem;
  margin-bottom: 2rem;
  padding: 1.5rem;
  background-color: #fcfaf5;
  border-radius: 4px;
  box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
