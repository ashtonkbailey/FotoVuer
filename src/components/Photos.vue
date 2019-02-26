<template>
  <div>
    <div v-if="loading">
      <img src="../src/assets/loader.gif"/>
      Loading.....
    </div>
    <ul 
      v-if="photos.length"
      class="photo-list">
      <SinglePhoto
        v-for="photo in photos"
        :key="photo.id"
        :photo="photo"
      />
    </ul>
    <h3 v-else>use the search bar to see some sick pics.</h3>
    <SearchInput
      v-model="term"
      placeholder="type a search term and click 'enter'"
      @keydown.enter="searchPhotos"
    />
  </div>
</template>

<script>
  import SinglePhoto from './SinglePhoto.vue'
  import SearchInput from './SearchInput.vue'
  import { key } from '../key.js'

  export default {
    name: 'Photos',
    components: {
      SinglePhoto, SearchInput
    },
    data() {
      return {
        photos: [],
        term: '',
        loading: false
      }
    },
    methods: {
      searchPhotos() {
        this.loading = true;
        fetch(`https://api.unsplash.com/search/photos?page=1&query=smoke&client_id=${key}`)
          .then((response) => {
            this.loading = false;
            response.json();
          })
          .then(data => this.photos = data.results)
          .catch((error) => {
            this.loading = false;
            console.error(error);
          })
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .photo-list {
    
  }
</style>
