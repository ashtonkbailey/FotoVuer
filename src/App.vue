<template>
  <div id="app">
    <h1 :class="title">FotoVuer</h1>
    <h3 :class="search-word">results for ''</h3>
    <Photos />
    <form>
      <input />
      <button>search</button>
    </form>
  </div>
</template>

<script>
import Photos from './components/Photos.vue'

export default {
  name: 'app',
  components: {
    Photos
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
