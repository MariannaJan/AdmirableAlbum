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
@import "https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"

</style>
