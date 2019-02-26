<template>
  <ul 
    v-if="photos.length"
    class="photo-list">
    <SinglePhoto />
  </ul>
  <h3 v-else>use the search bar to see some sick pics.</h3>
  <SearchInput />
</template>

<script>
  import SinglePhoto from './SinglePhoto.vue'
  import SearchInput from './SearchInput.vue'

  export default {
    name: 'Photos',
    components: {
      SinglePhoto, SearchInput
    },
    data() {
      return {
        photos: []
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .photo-list {
    
  }
</style>
