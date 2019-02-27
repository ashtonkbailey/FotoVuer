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
    flex: 0 0 20em;
  height: 20em;
  margin: 1em;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0.1em dashed #000;
  border-radius: 50%;
  transition: transform 0.3s ease-in-out;
  }
  .photo:first-of-type {
    opacity: 0;
  }
  .photo:last-of-type {
    opacity: 0;
  }
</style>
