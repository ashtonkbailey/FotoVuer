<template>
  <ul class="photo-list">
    <SinglePhoto />
  </ul>
</template>

<script>
  import SinglePhoto from './SinglePhoto.vue'

  export default {
    name: 'Photos',
    components: {
      SinglePhoto
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .photo-list {
    
  }
</style>
