<template>
  <div>
    <input type="search" placeholder="Search Song or Author"
      v-model="searchSong"
      @keyup="search()"
    />
  </div>
</template>

<script>
export default {
  name: 'SearchBar',

  data() {
    return {
        searchSong: '',
    }
  },

  methods: {
        search() {
            this.$emit('search', this.searchSong);
        }
    }
}
</script>

<style>

</style>