<template>
  <ul 
    v-if="photos.length"
    class="photo-list">
    <SinglePhoto />
  </ul>
  <h3 v-else>use the search bar to see some sick pics.</h3>
</template>

<script>
  import SinglePhoto from './SinglePhoto.vue'

  export default {
    name: 'Photos',
    components: {
      SinglePhoto
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
