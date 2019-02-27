<template>
  <div>
    <div v-if="loading">
      <img src="../assets/loader.gif"/>
      Loading.....
    </div>
    <div class="carousel-view">
      <transition-group
        tag="div"
        v-if="photos.length"
        class="photo-list"
      >
        <SinglePhoto
          v-for="photo in photos"
          :key="photo.id"
          :photo="photo"
        />
      </transition-group>
      <h2
        v-else
        class="no-photos"
      >use the search bar to browse photos</h2>
    </div>
    <SearchInput
      v-model="term"
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
        fetch(`https://api.unsplash.com/search/photos?page=1&query=${this.term}&client_id=${key}`)
          .then((response) => {
            this.loading = false;
            return response.json();
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
  .carousel-view {
    height: 75vh;
  }
  .photo-list {
    
  }
</style>
