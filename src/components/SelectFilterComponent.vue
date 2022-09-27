<template>
  <div>
    <label for="genre">Choose a Genre</label>

    <select name="genre" id="genre"
        v-model="filterOptions"
        @click="getNewFilter()"    
    >
        <option value="">All</option>
        <option value="Pop">Pop</option>
        <option value="Rock">Rock</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
    name: 'SearchFilter',

    data() {
        return {
            filterOptions: '',
        }
    },

    computed: {
        newFilter() {
            return this.filterOptions;
        }
    },

    methods: {
        getNewFilter() {
            this.$emit('filter', this.newFilter);
        }
    }
}
</script>

<style>

</style>