<template>
  <li class="photo">
    <img :src="photo.urls.small" />
  </li>
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
