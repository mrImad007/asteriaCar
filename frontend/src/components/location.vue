<template>
    <div>
      
      <transition-group name="fade" tag="div" >
        <div v-for="i in [currentIndex]" :key="i" class="location">
          <h1>Location de voiture</h1>
          <img :src="currentImg" />
        </div>
    </transition-group>
    </div>
  </template>
  
  <script>
  export default {
    name: "locationComponent",
    data() {
      return {
        images: [
        require("../assets/location_car/image1.png"),
        require("../assets/location_car/image2.png"),
        require("../assets/location_car/image3.png"),
        require("../assets/location_car/image4.png"),
        ],
        timer: null,
        currentIndex: 0
      };
    },
    mounted: function() {
      this.startSlide();
    },
    methods: {
      startSlide: function() {
        this.timer = setInterval(this.next, 3000);
      },
      next: function() {
        this.currentIndex += 1;
      },
      prev: function() {
        this.currentIndex -= 1;
      }
    },
    computed: {
      currentImg: function() {
        return this.images[Math.abs(this.currentIndex) % this.images.length];
      }
    }
  };
  </script>
  
  <style lang="scss">

  .location{
    opacity: 50%;
    &:hover{
      opacity: 100%;
    }
  }
  
  .fade-enter,
  .fade-leave-to {
    visibility: hidden;
    transition: all 0ms ease;
    width: 100%;
  }
  
  img {
    height: 100%;
    width: 100%;
  }

  h1{
    position: absolute;
    color: rgba(173, 10, 10, 1);
    
  }
  
  </style>