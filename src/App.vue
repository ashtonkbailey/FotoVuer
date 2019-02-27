<template>
  <div id="app">
    <h1 class="title">FotoVuer</h1>
    <h3 class="search-word">results for ''</h3>
    <Photos />
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
body {
  background: linear-gradient(80deg, #101d37, #09090a);
}
#app {
  color: #afcad1;
  font-family: 'Open Sans', sans-serif;
  height: 100vh;
  margin: 0;
  text-align: center;
  width: 100%;
}
.title {
  color: #fea18a;
  font-family: 'Nova Flat', cursive;
  font-size: 3rem;
  margin-top: 0;
}
</style>
