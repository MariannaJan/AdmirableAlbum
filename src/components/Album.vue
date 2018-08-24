<template>
<div>
  <div class="row my-3 ">
    <h1 class='title col'>Flood 2010 <span class="font-italic">Park in Wloclawek</span></h1>
  </div>
    <div class="btn-group mb-3" role="group">
    <button class="btn btn-outline-warning" @click="prev">Previous</button> <button class="btn btn-outline-warning" @click="next">Next</button>
  </div> 
  <div class="row">
    <transition-group name='fade' tag='div'>
    <div v-for="number in [currentNumber]" :key='number' class="polaroid">
        <img :src="images[Math.abs(currentNumber) % images.length]" 
        v-on:mouseover="stopRotation" 
        v-on:mouseout="startRotation" 
        /> 
    </div>
    </transition-group>
  </div>
 
</div>
</template>

<script>
export default {
  name: 'Album',
  data() {
    return {images: [ require('../assets/Photos/park1.jpg'),require('../assets/Photos/park2.jpg'),require('../assets/Photos/park3.jpg'),
                      require('../assets/Photos/park4.jpg'),require('../assets/Photos/park5.jpg'),require('../assets/Photos/park6.jpg'),
                      require('../assets/Photos/park7.jpg'),require('../assets/Photos/park8.jpg'),require('../assets/Photos/park9.jpg'),
                      require('../assets/Photos/park10.jpg'),require('../assets/Photos/park11.jpg'),require('../assets/Photos/park12.jpg'),
                      require('../assets/Photos/park13.jpg'),require('../assets/Photos/park14.jpg'),require('../assets/Photos/park15.jpg'),require('../assets/Photos/park16.jpg')
                      ],
    currentNumber: 0,
    timer: null }
  },
  mounted: function () {
    this.startRotation();
  },
  methods: {
    startRotation: function () {
      this.timer = setInterval(this.next, 3000);
    },
    stopRotation: function () {
      clearTimeout(this.timer);
      this.timer = null;
    },
    next: function () {    
      this.currentNumber += 1;      
    },
    prev: function () {
      this.currentNumber -= 1;
    }
  }
}
</script>

<style scoped>
.title {
  color: #6f6949;
}
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
.btn-outline-warning, .btn-outline-warning:hover, .btn-outline-warning:active, .btn-outline-warning:visited {
    background-color: #6f6949 !important;
    border-color: black !important;
    color: #44422d !important;
    box-shadow: none !important;
}
.btn-outline-warning:hover {
  color: black !important;
  box-shadow: none !important;
}
.fade-enter-active, .fade-leave-active {
 transition: all 1.8s ease;
 overflow: hidden;
 visibility: visible;
 opacity: 1;
 position: absolute;
 }
 
.fade-leave-active {
    transform: scale(.1) rotateZ(-90deg);
    -moz-transform: scale(.1) rotateZ(-90deg);
    -webkit-transform: scale(.1) rotateZ(-90deg);
    -o-transform: scale(.1) rotateZ(-90deg);
    border-radius: 50%;
}
.fade-enter, .fade-leave-to {
 opacity: 0;
 visibility: hidden;
}
</style>
