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
      >
        use the search bar below to browse photos
      </h2>
    </div>
    <div class='photo-controls'>
      <button
        class='carousel-controls'
        @click="previous"
      >
        prev
      </button>
      <SearchInput
        v-model="term"
        @keydown.enter="searchPhotos"
      />
      <button
        class='carousel-controls'
        @click="next"
      >
        next
      </button>
    </div>
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
      },
      next () {
        const first = this.photos.shift()
        this.photos = this.photos.concat(first)
      },
      previous () {
        const last = this.photos.pop()
        this.photos = [last].concat(this.photos)
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .carousel-view {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 73vh;
  }
  .photo-list {
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    width: 40em;
    min-height: 25em;
  }
  .photo-controls {
    display: flex;
    flex-direction: row;
    width: 100%;
  }
</style>
