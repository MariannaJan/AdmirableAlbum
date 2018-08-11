<template>
<div>
  <div class="row">
    <p>Some text</p>
  </div>
  <div class="row">
    <div class="polaroid pull-left">
        <img src="@/assets/Photos/park1.jpg" />
    </div>
  </div>
</div>
</template>

<script>

export default {
  name: 'Album',
}
</script>

<style scoped>

img {
    filter: sepia(90%) brightness(0.6) blur(2px);
    border: 1px solid #44422d;
    }
  img:hover {
    filter: none;
    }
.polaroid {
	padding: 10px 10px 10px 10px;
  background-color: #44422d;
	-webkit-box-shadow: 2px 2px 3px rgba(135, 139, 144, 0.4);
	-moz-box-shadow: 2px 2px 3px rgba(135, 139, 144, 0.4);
	box-shadow: 2px 2px 3px black;
}
.pull-left.polaroid {
	-webkit-transform: rotate(-9deg);
	-moz-transform: rotate(-9deg);
	transform: rotate(-9deg);
}

</style>
