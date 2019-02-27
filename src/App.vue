<template>
  <div id="app">
    <h1 class="title">FotoVuer</h1>
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
  overflow: hidden;
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
  font-size: 4rem;
  text-shadow: 0 1px 0 #f25348, 0 2px 0 #ea746b, 0 3px 0 #e05a56, 0 4px 0 #cf8270, 0 5px 0 #e28976, 0 6px 1px rgba(0,0,0,.1), 0 0 5px rgba(0,0,0,.1), 0 1px 3px rgba(0,0,0,.3), 0 3px 5px rgba(0,0,0,.2), 0 5px 10px rgba(0,0,0,.25), 0 10px 10px rgba(0,0,0,.2), 0 20px 20px rgba(0,0,0,.15);
}
</style>
