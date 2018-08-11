<template>
  <div id="app" class="container">
    <Album/>
  </div>
</template>

<script>
import Album from './components/Album.vue'

export default {
  name: 'app',
  components: {
    Album
  }
}
</script>

<style>
@import "https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css";

html {
    height: 100%;
}

body {
  margin: 0;
  min-height: 100%;
  background: radial-gradient(#44422d, black);
  
  background-repeat: no-repeat;
}

</style>
