<template>
  <div class="photo">
    <img :src="photo.urls.small" />
  </div>
</template>

<script>
  export default {
    name: 'SinglePhoto',
    props: {
      photo: {
        type: Object,
        required: true
      }
    }
  }
</script>

<style scoped>
  .photo {
    list-style: none;
  }
</style>
