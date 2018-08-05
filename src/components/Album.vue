<template>
  <div class>
        <a href="#">
        <img src="@/assets/Photos/park1.jpg" />
        <p>Some text <span>here</span>.</p>
    </a>
  </div>
</template>

<script>
export default {
  name: 'Album',
  props: {
    msg: String
  }
}
</script>

<style scoped>
        img {
            width: 50%;
            height: 50%;
            filter: sepia(90%) brightness(0.6) blur(2px);
            }
        a:hover img {
            filter: none;
            }
        a:hover span {
            font-weight: bold;
        }
</style>
